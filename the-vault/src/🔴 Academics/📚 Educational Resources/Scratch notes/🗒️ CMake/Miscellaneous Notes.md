---
title: Miscellaneous Notes
created: 2023-09-12 03:27
updated: 2024-04-14T00:24
authors:
  - Edmund Leibert III
tags:
  - 🔴-academic/📚-educational-resource/name/🗒️-cmake/🔖/miscellaneous-notes
  - 🔴-academic/📚-educational-resource/format/miscellaneous
  - 🔴-academic/📚-educational-resource/discipline/computer-science/technology/cmake
  - study-note
cards-deck: 🔴 Academic::📚 Educational Resource::🗒️ CMake::Miscellaneous Notes
banner: "![[https://i.imgur.com/8yW9ZIK.png]]"
banner_y: 0
---

#  Miscellaneous Notes

---

> [!ABSTRACT]+ 
> Miscellaneous scratch notes pertaining to [Angular](https://angular.dev/) [@Angular].
> 
> These notes are primarily structured in a Q&A format, making it easy to follow and learn. Corresponding Anki flashcards are available, enabling efficient revision and reinforcement of the concepts.

---

 > [!INFO]+
 > **Previous Note(s)**: 
 > 

---

﹇<br>
What languages does CMake support? 

#anki-card 

Supported languages are:
- C, CXX (i.e. C++)
- CSharp (i.e. C#)
- CUDA
- OBJC (i.e. Objective-C)
- OBJCXX (i.e. Objective-C++)
- Fortran
- HIP
- ISPC
- Swift
- ASM
- ASM_NASM
- ASM_MARMASM
- ASM_MASM
- ASM-ATT

⌂
<br>﹈<br>^1702345012963


﹇<br>
What are some potential ['cmake clean' commands to clear up CMake output](https://stackoverflow.com/questions/9680420/looking-for-a-cmake-clean-command-to-clear-up-cmake-output)?

#anki-card

CMake 3.X offers a 'clean' target:
```cmake
cmake --build C:/foo/build/ --target clean
```

From the CMake docs for 3.0.2:
```cmake
--clean-first  = Build target 'clean' first, then build.
                 (To clean only, use --target 'clean'.)
```

⌂
<br>﹈<br>^1702345012968


﹇<br>
In CMake, how can you configure the compiler flags?

#anki-card 

In CMake, you can configure the compiler flags in several ways:

1. **Appending to CMake Variables**: You can append flags to the corresponding CMake variables. [For example, if you want to add a flag for C++ compilation, you can do so by appending it to `CMAKE_CXX_FLAGS`](https://stackoverflow.com/questions/11783932/how-do-i-add-a-linker-or-compile-flag-in-a-cmake-file)[1](https://stackoverflow.com/questions/11783932/how-do-i-add-a-linker-or-compile-flag-in-a-cmake-file). Here’s an example:
    
```cmake
SET (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${MYCOMPILE_FLAGS}")
```
    
2. **Using `add_definitions`**: This method is not clean but easy and convenient. [It works for both compiler flags, C & C++ at once](https://stackoverflow.com/questions/11783932/how-do-i-add-a-linker-or-compile-flag-in-a-cmake-file)[1](https://stackoverflow.com/questions/11783932/how-do-i-add-a-linker-or-compile-flag-in-a-cmake-file). Here’s an example:
    
```cmake
add_definitions (${MYCOMPILE_FLAGS})
```
    
3. [**Using Target Properties**: You can use target properties if you know the target name](https://stackoverflow.com/questions/11783932/how-do-i-add-a-linker-or-compile-flag-in-a-cmake-file)[1](https://stackoverflow.com/questions/11783932/how-do-i-add-a-linker-or-compile-flag-in-a-cmake-file). Here’s an example:
    
```cmake
get_target_property (TEMP ${THE_TARGET} COMPILE_FLAGS)
if (TEMP STREQUAL "TEMP-NOTFOUND")  
  SET (TEMP "") # Set to empty string
else ()  
  SET (TEMP "${TEMP} ") # A space to cleanly separate from existing content
endif ()
SET (TEMP "${TEMP}${MYCOMPILE_FLAGS}" )
set_target_properties (${THE_TARGET} PROPERTIES COMPILE_FLAGS ${TEMP})
```
    

[Please note that it’s generally recommended to use `set_compile_options`, `target_compile_options`, `add_compile_definitions`, and `target_compile_definitions` instead of manually setting `CMAKE_*_FLAGS`](https://stackoverflow.com/questions/59107988/correct-way-to-handle-compiler-flags-when-using-cmake)[2](https://stackoverflow.com/questions/59107988/correct-way-to-handle-compiler-flags-when-using-cmake).

⌂
<br>﹈<br>^1702345012972

﹇<br>
Would it be correct to say:

> the naming convention of a **CMake** project name _is_

…or…

> the naming convention<u>s</u> of a **CMake** project name _are_

#anki-card #🔴-academic/📚-educational-resource/discipline/computer-science/technology/cmake 

Both phrases can be correct depending on the context.

If you’re referring to a single rule or standard that applies to the naming of a CMake project, you would use the singular form: “the **naming convention** of a CMake project name”.

However, if you’re referring to multiple rules or standards that apply to the naming of a CMake project, you would use the plural form: “the **naming conventions** of a CMake project name”.

> [!INFO] NOTE
> In practice, naming often involves multiple rules or standards, so the plural form (“naming conventions”) is used more frequently. 
> But again, the choice between singular _and_ plural <b>depends on the <u>specific context</u></b>.

⌂
<br>﹈<br>^1707555962297


﹇<br>
As of February 2024, what are the proper naming convention for **CMake** projects?

#anki-card 

The naming convention for CMake projects is not strictly defined, but there are some common practices:

1. [**Project Names**: The `project()` command in CMake sets the name of the project](https://cmake.org/cmake/help/latest/command/project.html)[1](https://cmake.org/cmake/help/latest/command/project.html). [This name is stored in the `PROJECT_NAME` variable and also in the `CMAKE_PROJECT_NAME` variable when called from the top-level `CMakeLists.txt`](https://cmake.org/cmake/help/latest/command/project.html)[1](https://cmake.org/cmake/help/latest/command/project.html).
    
2. [**Target Names**: When defining library targets, it’s common to use lowercase letters with words separated by hyphens](https://cmake.org/cmake/help/latest/command/project.html)[2](https://stackoverflow.com/questions/48524359/naming-convention-for-components-and-namespaces-in-cmake). [For example: `add_library(foo-bar src1.cpp, src2.cpp)`](https://cmake.org/cmake/help/latest/command/project.html)[2](https://stackoverflow.com/questions/48524359/naming-convention-for-components-and-namespaces-in-cmake).
    
3. [**Namespaces**: When providing imported targets, these should be namespaced](https://cmake.org/cmake/help/latest/command/project.html)[2](https://stackoverflow.com/questions/48524359/naming-convention-for-components-and-namespaces-in-cmake). [CMake will recognize that values passed to `target_link_libraries()` that contain `::` in their name are supposed to be imported targets](https://cmake.org/cmake/help/latest/command/project.html)[2](https://stackoverflow.com/questions/48524359/naming-convention-for-components-and-namespaces-in-cmake). [For example: `add_library(Foo::Bar ALIAS foo-bar)`](https://cmake.org/cmake/help/latest/command/project.html)[2](https://stackoverflow.com/questions/48524359/naming-convention-for-components-and-namespaces-in-cmake).
    
4. [**Function Names**: CMake function names are typically all lowercase with words separated by underscores](https://discourse.cmake.org/t/naming-conventions-for-cmake-functions/4615)[3](https://discourse.cmake.org/t/naming-conventions-for-cmake-functions/4615). [For example: `ExternalData_add_test(...)`](https://cmake.org/cmake/help/latest/command/project.html)[3](https://discourse.cmake.org/t/naming-conventions-for-cmake-functions/4615).
    
5. **Consistency**: It’s recommended to follow a consistent naming style. [Snake_case is an accepted standard in the CMake community](https://www.educative.io/courses/modern-cmake-for-cpp/naming-conventions)[4](https://www.educative.io/courses/modern-cmake-for-cpp/naming-conventions).
    

Remember, these are just common practices and may vary between different projects. It’s always a good idea to check the specific guidelines for the project you’re working on.

⌂
<br>﹈<br>^1707555962305


---

## :EiZoteroItem: Bibliography

---

> [!INFO]+
> **Next Note(s):**

---
