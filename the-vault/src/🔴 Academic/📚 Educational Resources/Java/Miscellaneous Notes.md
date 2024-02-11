---
title: Miscellaneous Notes
created: 2023-09-03 08:46
updated: 2024-02-10T16:48
authors:
  - Edmund Leibert III
tags:
  - 🔴-academic/📚-educational-resources/name/🗒️-java/🔖/miscellaneous-notes
  - 🔴-academic/📚-educational-resources/format/miscellaneous
  - 🔴-academic/📚-educational-resources/discipline/computer-science/programming-language/java
  - study-note
cards-deck: 🔴 Academic::📚 Educational Resources::🗒️ Java::Miscellaneous Notes
banner: "![[https://i.imgur.com/8NiD8Cf.jpeg]]"
banner_y: 0
---

# Miscellaneous Notes

---

> [!INFO]+ Note 
> This **page** contains **miscellaneous** _scratch notes_ pertaining to **[Java](https://www.zotero.org/)** [@ZoteroYourPersonal].
> 
> These notes are primarily structured in a Q&A format, making it easy to follow and learn. Corresponding [**Anki**](https://apps.ankiweb.net/) flashcards are available, enabling efficient revision and reinforcement of the concepts [@ankitectsAnkiPowerfulIntelligent].

---

> [!INFO]+ 
> **Previous Notes**:
> 

---


﹇<br>
As of Feb. 10, 2024 04:06:51 PM, what is the standard **convention** when **naming variables** in **Java**?

#card 

In Java, variable names should adhere to the following conventions:

- [They should start with a lowercase letter](https://www.javatpoint.com/java-naming-conventions)[1](https://www.javatpoint.com/java-naming-conventions) [2](https://www.geeksforgeeks.org/java-naming-conventions/).
- If the name contains multiple words, it should be in camelCase. [This means the first word is all lowercase, and the first letter of each subsequent word is capitalized](https://www.javatpoint.com/java-naming-conventions)[1](https://www.javatpoint.com/java-naming-conventions) [2](https://www.geeksforgeeks.org/java-naming-conventions/). For example, `firstName`, `lastName`.
- [Variable names should not start with special characters like & (ampersand), $ (dollar), _ (underscore)](https://www.javatpoint.com/java-naming-conventions) [1](https://www.javatpoint.com/java-naming-conventions).
- [One-character variable names should be avoided except for temporary variables](https://www.javatpoint.com/java-naming-conventions) [2](https://www.geeksforgeeks.org/java-naming-conventions/).
- [Variable names should be meaningful and mnemonic, i.e., designed to indicate to the casual observer the intent of its use](https://www.javatpoint.com/java-naming-conventions) [2](https://www.geeksforgeeks.org/java-naming-conventions/).
- [Java keywords cannot be used as variable names](https://www.javatpoint.com/java-naming-conventions)[3](https://www.geeksforgeeks.org/rules-for-variable-declaration-in-java/).

Here’s an example:

```java
class Employee {
    // Good variable names
    String firstName;
    String lastName;
    int age;

    // Avoid one-character variable names
    int i;  // Not recommended
}
```

[These conventions make your code easier to read for yourself and other programmers](https://www.javatpoint.com/java-naming-conventions) [1](https://www.javatpoint.com/java-naming-conventions).

⌂
<br>﹈<br>^1707611441293

﹇<br>
In software engineering, what is an **interface**? How are interfaces generally implemented in Java? Lastly, what is the `Comparable` interface in Java and what is it used for?

#card 

In **software engineering**, an interface can be thought of as a contract between the system and the environment. In a computer program, the **system** is the function or module in question, and the **environment** is the rest of the project. The interface formally describes what can pass between the system and the environment. It's a shared boundary across which two or more separate components of a computer system exchange information.

In the context of **Java**, an interface is a special type of class that only contains abstract methods. It's a blueprint of a behavior. A Java interface contains static constants and abstract methods. There can be **only** abstract methods in the Java interface, **not** the method body. It is used to achieve abstraction and multiple inheritances in Java.

Here's an example of how to implement an interface in Java:

```java
interface Animal {
    void eat();
    void sleep();
}

class Dog implements Animal {
    public void eat() {
        System.out.println("Dog eats");
    }

    public void sleep() {
        System.out.println("Dog sleeps");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog();
        myDog.eat();
        myDog.sleep();
    }
}
```

In this example, Animal is an interface with two methods: eat and sleep. The Dog class implements the Animal interface, so it must provide implementations for the eat and sleep methods. If a class implements an interface but doesn't provide implementations for all its methods, it must be declared abstract.

⌂
<br>﹈<br>^1707611441305

As of Feb. 10, 2024 04:31:30 PM, a {1:Java interface} only contains {2:static constants} and {2:abstract methods}.
^1707611622475

As of Feb. 10, 2024 04:29:34 PM, in the context of **Java**, an {1:interface} is a special type of class that {2:only contains abstract methods}.
^1707611441310

As of Feb. 10, 2024 04:32:55 PM, in the context of **Java**, if a class {1:implements an interface but doesn’t provide implementations for all its methods{, it must be declared {2:abstract}.
^1707611622480

As of Feb. 10, 2024 04:34:22 PM, the the context of **Java**, the {1:`Object`} class is the {2:superclass for all classes in Java}.
^1707611754722

Got it, here are the flashcards formatted in the requested style:

﹇<br>
What is an interface in software engineering?

#card

An interface can be thought of as a contract between the system and the environment. In a computer program, the ‘system’ is the function or module in question, and the ‘environment’ is the rest of the project. The interface formally describes what can pass between the system and the environment. It’s a shared boundary across which two or more separate components of a computer system exchange information.  

⌂
<br>﹈<br>^1707612511168

﹇<br>
What is an interface in Java?

#card

In Java, an interface is a special type of class that only contains abstract methods. It’s a blueprint of a behavior. A Java interface contains static constants and abstract methods. There can be only abstract methods in the Java interface, not the method body. It is used to achieve abstraction and multiple inheritances in Java.

⌂
<br>﹈<br>^1707612511178

﹇<br>
How to implement an interface in Java?

#card

A class implements an interface by using the `implements` keyword followed by the interface name. The class must provide implementations for all the methods declared in the interface. If a class implements an interface but doesn’t provide implementations for all its methods, it must be declared abstract.

⌂
<br>﹈<br>^1707612511182

﹇<br>
What is the purpose of the `equals()` method in Java?

#card

The `equals()` method is typically used to compare objects for equality. It’s defined in the `Object` class, which is the superclass for all classes in Java. Therefore, all objects in Java inherit this method and can use it to compare for equality.

⌂
<br>﹈<br>^1707612511187

﹇<br>
How do you compare primitive types in Java?

#card 

For comparing primitive types, you should use the equality operator `==`. For example, `if (a == b)` would compare two integers `a` and `b`.
^1707612511194

⌂
<br>﹈<br>^1707612511199
