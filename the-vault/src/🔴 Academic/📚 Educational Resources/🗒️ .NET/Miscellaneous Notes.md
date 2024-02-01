---
title: Miscellaneous Notes
created: 2023-09-03 08:46
updated: 2024-01-31T19:33
authors:
  - Edmund Leibert III
tags:
  - 🔴-academic/📚-educational-resources/name/🗒️-net/🔖/miscellaneous-notes
  - 🔴-academic/📚-educational-resources/format/miscellaneous
  - 🔴-academic/📚-educational-resources/discipline/computer-science/developer-platform/net
  - study-note
cards-deck: 🔴 Academic::📚 Educational Resources::🗒️ .NET::Miscellaneous Notes
banner: "![[the-vault/assets/banners/dotnet.jpeg]]"
banner_y: 0
---

# Miscellaneous Notes

---

> [!INFO]+ Note 
> This **page** contains **miscellaneous** _scratch notes_ pertaining to **[.NET](https://dotnet.microsoft.com/en-us/)**. [@NETBuildTest]
> 
> These notes are primarily structured in a Q&A format, making it easy to follow and learn. Corresponding [**Anki**](https://apps.ankiweb.net/) flashcards are available, enabling efficient revision and reinforcement of the concepts. 

---

> [!INFO]+ Note
> **Previous Note(s)**:
> 

---

﹇<br>
In brief, what is Microsoft’s **.NET**?

#card 

**.NET** is a free, cross-platform, [open-source developer platform](https://github.com/dotnet/core) for building [many kinds of applications](https://learn.microsoft.com/en-us/dotnet/core/apps). It can run programs written in [multiple languages](https://learn.microsoft.com/en-us/dotnet/fundamentals/languages), with [C#](https://learn.microsoft.com/en-us/dotnet/csharp/) being the most popular. It relies on a [high-performance](https://devblogs.microsoft.com/dotnet/category/performance/) runtime that is used in production by many [high-scale apps](https://devblogs.microsoft.com/dotnet/category/developer-stories/). [@genevievewarrenIntroductionNETNET2024]

⌂
<br>﹈<br>


﹇<br>
What is **DocTo**?

#card #🔴-academic/📚-educational-resources/discipline/computer-science/technologies/docto

**DocTo** is a simple utility for converting a Microsoft Word Document ‘.doc’ and Microsoft Excel ‘.xls’ files to any other supported format such as `.txt`, `.csv`, `.rtf`, and `.pdf`. [@tobyallenDocToXLSTo]

It additionally has the following features:
- Can also be used to convert `.txt`, `.rtf`, `.csv` to `.doc`, `.xls` or `.pdf` format.
- Can be used to convert older word documents to latest format.

> [!CAUTION]+ Warning
> Must have Microsoft Word or Excel installed on host machine.

⌂
<br>﹈<br>


﹇<br>
Using the [DocTo](https://github.com/tobya/DocTo) library, how can I export a `.docx` to a `.pdf` in the command line? [@tobyallenDocToXLSTo]

#card #🔴-academic/📚-educational-resources/discipline/computer-science/technologies/docto

```pwsh
docto -f C:\Directory\MyFile.doc -O "C:\Output Directory\MyTextFile.pdf" -T wdFormatPDF
```

⌂
<br>﹈<br>^1702296738200

﹇<br>
What does JSON stand for?

#card #🔴-academic/📚-educational-resource/discipline/computer-science/technology/json

**J**ava**S**cript **O**bject **N**otation

⌂
<br>﹈<br>^1702296738213

﹇<br>
What _namespace_ in .NET provides functionality for _serializing_ to and _deserializing_ form **J**ava**S**cript **O**bject **N**otation (JSON)?

#card #🔴-academic/📚-educational-resources/discipline/computer-science/programming-language/csharp

[The `System.Text.Json` namespace in .NET provides high-performance, low-allocating, and standards-compliant capabilities to process JavaScript Object Notation (JSON)](https://learn.microsoft.com/en-us/dotnet/api/system.text.json?view=net-8.0) [@dotnet-botSystemTextJson]. [It includes serializing objects to JSON text and deserializing JSON text to objects, with UTF-8 support built-in](https://learn.microsoft.com/en-us/dotnet/api/system.text.json?view=net-8.0)  [@dotnet-botSystemTextJson]. [It also provides types to read and write JSON text encoded as UTF-8, and to create an in-memory document object model (DOM) for random access of the JSON elements within a structured view of the data](https://learn.microsoft.com/en-us/dotnet/api/system.text.json?view=net-8.0) [@dotnet-botSystemTextJson].

[Here’s an example of how to use the `System.Text.Json` namespace to serialize an object to JSON](https://learn.microsoft.com/en-us/dotnet/standard/serialization/system-text-json/how-to) [@genevievewarrenHowSerializeJSON2023]:

```csharp
using System;
using System.Text.Json;

namespace SerializeBasic
{
    public class WeatherForecast
    {
        public DateTimeOffset Date { get; set; }
        public int TemperatureCelsius { get; set; }
        public string? Summary { get; set; }
    }

    public class Program
    {
        public static void Main()
        {
            var weatherForecast = new WeatherForecast
            {
                Date = DateTime.Parse("2019-08-01"),
                TemperatureCelsius = 25,
                Summary = "Hot"
            };

            string jsonString = JsonSerializer.Serialize(weatherForecast);
            Console.WriteLine(jsonString);
        }
    }
}
```

[This code creates a `WeatherForecast` object, serializes it to a JSON string using the `JsonSerializer.Serialize` method, and then writes the JSON string to the console](https://learn.microsoft.com/en-us/dotnet/standard/serialization/system-text-json/how-to) [@genevievewarrenHowSerializeJSON2023]. [The output will be a minified JSON string](https://learn.microsoft.com/en-us/dotnet/standard/serialization/system-text-json/how-to) [@genevievewarrenHowSerializeJSON2023].

When you run this program, it will print a JSON string to the console that represents the `WeatherForecast` object. The JSON string will look something like this:

```json
{"Date":"2019-08-01T00:00:00","TemperatureCelsius":25,"Summary":"Hot"}
```

This string represents a `WeatherForecast` with a `Date` of “2019-08-01”, a `TemperatureCelsius` of 25, and a `Summary` of “Hot”

⌂
<br>﹈<br>^1702296738224

﹇<br>
In the context of **C#**,  and more generally **.NET**, does the _serialized form_ include any information about an object’s associated _methods_?

#card #🔴-academic/📚-educational-resources/discipline/computer-science/programming-language/csharp 

[In C#, and generally in most programming languages, serialization does **not** include an object’s methods](https://stackoverflow.com/questions/2767893/are-methods-also-serialized-along-with-the-data-members-in-net) [\[1\]](https://stackoverflow.com/questions/2767893/are-methods-also-serialized-along-with-the-data-members-in-net) [\[2\]](https://stackoverflow.com/questions/3042665/what-is-the-meaning-of-serialization-in-programming-languages). [Serialization is the process of converting the state of an object into a form that can be persisted or transported](https://learn.microsoft.com/en-us/dotnet/standard/serialization/) [\[3\]](https://learn.microsoft.com/en-us/dotnet/standard/serialization/) [\[4\]](https://www.c-sharpcorner.com/article/serialization-and-deserialization-in-c-sharp/). [The serialized form includes only the data members (fields and properties) of the object](https://stackoverflow.com/questions/2767893/are-methods-also-serialized-along-with-the-data-members-in-net) [\[1\]](https://stackoverflow.com/questions/2767893/are-methods-also-serialized-along-with-the-data-members-in-net) [\[2\]](https://stackoverflow.com/questions/3042665/what-is-the-meaning-of-serialization-in-programming-languages).

Here’s an example to illustrate this. Consider a class `Person` that is defined in a file `Person.cs`, inside a namespace `MyApp.Models`, with properties and a method:

```csharp
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }

    public string GetGreeting()
    {
        return $"Hello, my name is {Name} and I am {Age} years old.";
    }
}
```

Now, let’s create an instance of this class and serialize it:

```csharp
using System;
using System.Text.Json;
using MyApp.Models; // Included the namespace where Person class is defined

public class Program
{
    public static void Main()
    {
        var person = new Person
        {
            Name = "John Doe",
            Age = 30
        };

        string jsonString = JsonSerializer.Serialize(person);
        Console.WriteLine(jsonString);
    }
}
```

When you run this program, it will print a JSON string to the console that represents the `Person` object. The JSON string will look something like this:

```json
{"Name":"John Doe","Age":30}
```

As you can see, the serialized JSON string includes the values of the `Name` and `Age` properties, but it does not include any information about the `GetGreeting()` method. [This is because serialization is about capturing the state (data) of an object, not its behavior (methods)](https://stackoverflow.com/questions/2767893/are-methods-also-serialized-along-with-the-data-members-in-net) [\[1\]](https://stackoverflow.com/questions/2767893/are-methods-also-serialized-along-with-the-data-members-in-net) [\[2\]](https://stackoverflow.com/questions/3042665/what-is-the-meaning-of-serialization-in-programming-languages).

⌂
<br>﹈<br>^1702296738231

﹇<br>
What is the definition of *serialization*?

#card-reverse 

The process of converting the state of an object, that is the values of its properties, into a form that can be stored or transmitted.

⌂
<br>﹈<br>^1702296738238

﹇<br>
What is the definition of *deserialization*?

#card-reverse 

Reconstructs an object from the deserialized form.

⌂
<br>﹈<br>^1702296738247

﹇<br>
As of 2023, what is the most prevalent encoding for data on the web and files on the disk?

#card 

UTF-8.

⌂
<br>﹈<br>^1702296738256

﹇<br>
Does UTF-8 support emojis?

#card 

Yes. Emojis are also characters from the UTF-8 alphabet: 😄 is 128516.

⌂
<br>﹈<br>^1702296738264

﹇<br>
What is the difference between **.NET Core**, **.NET Framework**, and **.NET**?

#card 

As of 2023, **.NET Core**, **.NET Framework**, and **.NET** are runtimes for building applications with **.NET**, sharing many of the same APIs called the .NET Standard [\[1\]](https://stackify.com/net-core-vs-net-framework/).
- **.NET Framework** is used for Windows desktop and server-based applications, including ASP.NET web applications [\[1\]](https://stackify.com/net-core-vs-net-framework/).
- **.NET Core** is used for server applications that run on Windows, Linux, and Mac, and supports the implementation of micro-services [\[1\]](https://stackify.com/net-core-vs-net-framework/).
	- **.NET Core** is more effective, fast, secure, flexible, and scalable than **.NET Framework**, and offers cross-platform performance and cloud deployment [\[1\]](https://stackify.com/net-core-vs-net-framework/).
	- **.NET Core** is open source and free to use [\[1\]](https://stackify.com/net-core-vs-net-framework/).
	- **.NET** is simply the new name for **.NET Core** (the “Core” part of the name was dropped for .NET Core v5.0)

⌂
<br>﹈<br>^1702296738273

﹇<br>
What is IIS?

#card 

IIS stands for Internet Information Services.
- It is an extensible web server created by Microsoft for use with the Windows NT family.
- IIS supports HTTP, HTTP/2, HTTPS, FTP, FTPS, SMTP and NNTP.

⌂
<br>﹈<br>^1702296738281

﹇<br>
What are HTTP, HTTP/2, HTTPS, FTP, FTPS, SMTP and NNTP?

#card 

These are all network protocols. They are designed to send/transfer information over a computer network and are a integral part of today’s internet.

⌂
<br>﹈<br>^1702296738290


﹇<br>
In the below code, why must the function `Main` have the `async Task<int>` attribute prepended to it? 

```csharp
internal abstract class MerriamWebsterAnkiFlashcardsGenerator
{
    private static HttpClient sharedClient = new()
    {
        BaseAddress = new Uri("https://jsonplaceholder.typicode.com"),
    };
    private static async Task<int> Main(string[] args)
    {
        Console.WriteLine("Hello, World!");
        using HttpResponseMessage response = await sharedClient.GetAsync("todos/3");
        response.EnsureSuccessStatusCode();      
        // print the response content to the console
        string responseContent = await response.Content.ReadAsStringAsync();
        Console.WriteLine(responseContent);    
        return 0;
    }
}
```

#card 

Asynchronous methods in C# typically return a `Task` or `Task<T>`, and they should be awaited with the `await` keyword.

When you use the `await` keyword on a Task, the method in which the `await` keyword is used must be marked as `async`. This is the signal to the compiler that the method contains an awaited asynchronous operation.

The `Main` method in this case returns a `Task<int>` because it's an async method and has a return type of `int`. If it didn't return a value, it would return `Task`.

⌂
<br>﹈<br>^1702296738298

﹇<br>
What does `Task<int>` signify in the context of an `async` method like `Main` in a C# program?

#card 

`Task<int>` is the return type of an asynchronous method that returns an integer. The `Task` represents an ongoing work that will eventually complete and produce a result of the type specified, in this case, an `int`. 

The `async` keyword allows the `await` keyword to be used in the method, which means the method will be executed asynchronously. The `Main` method returns `Task<int>` to indicate that it's an asynchronous method that will eventually produce an integer result (usually a status code).

⌂
<br>﹈<br>^1702296738308

﹇<br>
Why is the `Main` function in C# programs marked with `async` when using `HttpClient.GetAsync`?

#card 

 The `Main` function is marked with `async` because `HttpClient.GetAsync` is an asynchronous method, and any method that uses the `await` keyword must be marked as `async`. This lets the compiler know that the method contains an awaited asynchronous operation.

⌂
<br>﹈<br>^1702296738315

﹇<br>
What does `ReadAsStringAsync` do in the context of an `HttpResponseMessage`?

#card 

The `ReadAsStringAsync` method is used to asynchronously read the content from the HTTP response as a string. It reads the byte stream from the HTTP response and converts it into a string using the encoding specified in the HTTP response.

⌂
<br>﹈<br>^1702296738323

﹇<br>
What are the benefits of reading the content of an HTTP response asynchronously?

#card 

Reading the content asynchronously allows the application to do other work while waiting for the IO operation to complete. It makes the application more efficient and responsive, especially for IO-bound operations.

⌂
<br>﹈<br>^1702296738331

﹇<br>
What is the difference between thread-based operations and IO Completion Port (IOCP)-based operations?

#card 

Thread-based operations dedicate a thread for each IO operation, blocking it until the operation completes. This can be inefficient and resource-intensive. 

IOCP-based operations, on the other hand, use a pool of threads to handle multiple concurrent IO operations, increasing efficiency and performance.

⌂
<br>﹈<br>^1702296738341

﹇<br>
How does .NET implement IOCP-based operations?

#card 

While developers don't directly create and manage IOCPs in C#, the .NET Framework's implementation of async/await and Task uses IOCP under the hood on Windows. When these features are used, they automatically leverage IOCP-based operations.

⌂
<br>﹈<br>^1702296738348

﹇<br>
In .NET how do you ensure the success of a response?

#card 

Use the method `EnsureSuccessStatusCode()`. For example…

```csharp
using HttpResponseMessage response = await sharedClient.GetAsync("");
response.EnsureSuccessStatusCode();
```

⌂
<br>﹈<br>^1702296738358

In C#, the {`internal`} keyword is an access modifier that makes a member (like a method, property, or class) accessible only within its own assembly. An assembly in .NET is a unit of deployment like a `.dll` or `.exe` file.
^1702296738373

If you wanted to allow any code in any assembly to access a specific method, you would make it {`public`} instead. If you wanted to restrict access to only the containing class, you would use {`private`}. If you wanted to allow access from the containing class and any derived classes, you would use {`protected`}.
^1702296738384

﹇<br>
What is the default access modifier in C#?

#card 

`internal`

⌂
<br>﹈<br>^1702296738391

﹇<br>
What is the importance of `this` in the method argument of the below code? 

```csharp
internal static void WriteRequestToConsole(this HttpResponseMessage response)
{
    ...
}
```

#card 

The `this` keyword in front of `HttpResponseMessage response` indicates that `WriteRequestToConsole` is an extension method that can be called on instances of `HttpResponseMessage`. So, instead of calling the method like this:

```csharp
HttpResponseMessageExtensions.WriteRequestToConsole(response);
```

You can call it directly on an instance of `HttpResponseMessage`, like this:

```csharp
response.WriteRequestToConsole();
```

The latter is more intuitive and allows for more fluent and readable code, which is one of the main advantages of extension methods.

⌂
<br>﹈<br>^1702296738404

﹇<br>
What is the purpose of the `this` keyword in the argument list of a method in C#?

#card 

The `this` keyword in the argument list of a method is used to create an extension method in C#. An extension method is a static method that can be called as if it were an instance method of the extended type. The `this` keyword in front of the first parameter specifies the type the method will operate on. For example, in `WriteRequestToConsole(this HttpResponseMessage response)`, `this` indicates that `WriteRequestToConsole` is an extension method that can be called on instances of `HttpResponseMessage`.

⌂
<br>﹈<br>^1702296738415

﹇<br>
How would you write an extension method for the class `HttpResponseMessage`?

#card 

```csharp
ExtensionMethod(this HttpResponseMessage response)
```

⌂
<br>﹈<br>^1702296738431

﹇<br>
In C#, how would you create a global variable for the entire executable and that would be called rom other classes too?

#card 

In C#, you typically don't create global variables as you might in other programming languages. Instead, you would usually create a public static property in a static class. This property can then be accessed from any other class in your application.

Here is an example:

```csharp
public static class GlobalVariables
{
    public static string GlobalString { get; set; }
}
```

You can then access this property from any other class in your application, like this:

```csharp
GlobalVariables.GlobalString = "Hello, World!";
// Getting the value
string myString = GlobalVariables.GlobalString;
```

This will effectively give you a "global" variable, in the sense that it's accessible from any part of your application. However, be aware that using such globally accessible data can lead to problems if not managed carefully, such as making the code harder to understand and maintain, and potentially causing issues with concurrency in multi-threaded applications. It's often better to pass data explicitly through method parameters and return values, or use dependency injection to provide dependencies to classes that need them.

⌂
<br>﹈<br>^1702296738438

﹇<br>
Factoring in that, in .NET, it is considered better to pass data explicitly through method parameter and return values, or use dependency injection to provide dependencies to classes that need them, how should we handle a `HttpClient` instance?

#card 

Generally, a `HttpClient` instance is a good candidate for using a singleton or shared object in your application because of its connection pooling capabilities. In other words, reusing it for the lifetime of your application is recommended as per Microsoft’s guidelines.

⌂
<br>﹈<br>^1702296738448


﹇<br>
Can I have an async method in C# return a string?

#card 

Yes, an async method in C# can return a string. However, the method signature would need to return a `Task<string>`, because asynchronous methods need to return a `Task` or `Task<T>`.

Here's an example of how you can do this:

```csharp
public async Task<string> GetStringAsync() {
	await Task.Delay(1000);  // simulate async work with a delay     
	return "Hello, World!"; 
} 
private static async Task Main(string[] args) {     
	string result = await GetStringAsync();     
	Console.WriteLine(result);  // Outputs: Hello, World! 
}
```

⌂
<br>﹈<br>^1702296738457

﹇<br>
What does the method `public async Task GetStringAsync()` return?

#card 

It returns nothing.

⌂
<br>﹈<br>^1702296738465


﹇<br>
What does SOAP stand for in the context of .NET and software engineering in general?

#card 

To be filled.

⌂
<br>﹈<br>^1702296738473

﹇<br>
What does SDLC stand for in the context of .NET and the general context of software engineering? 

#card 

In the context of software engineering, SDLC stands for:

**S**oftware<br>
**D**evelopment<br> 
**L**ife-**C**ycle. <br>

It is a well defined sequence of step to not only create a software product, but ensure its longevity and continuous support.

⌂
<br>﹈<br>^1702296738480


﹇<br>
What process generally does SDLC entail?

#card 

The process generally follows several stages, including…
- planning
- requirement analysis
- design
- development
- testing
- deployment
- maintenance

⌂
<br>﹈<br>^1702296738488

﹇<br>
What does distributed development entail in the context of C#/.NET development?

#card 

Distributed development refers to the practice of developing software in a distributed computing environment, where different components of a software system can run on different systems (or servers), potentially across different locations.

Here are a few elements it might entail in the context of C# and .NET development:
1. **Microservices:** One common approach to distributed development is microservices architecture, where each service runs independently but communicates with others. Each service would have its own database and would be loosely coupled with the other services.
2. **Communication Between Services:** Distributed development requires mechanisms for the different services to communicate with each other. This might include using HTTP/REST, gRPC (a high-performance, open-source framework developed by Google), or even a message bus such as RabbitMQ or Azure Service Bus.
3. **Distributed Databases:** Your application might also interact with databases that are distributed across different locations. You'd need to understand concepts like data replication, sharding, and consistency models.
4. **Containerization and Orchestration:** Tools like Docker are often used to package and distribute the individual components of a distributed system. Orchestration tools like Kubernetes help manage these containers, handling deployment, scaling, and management.
5. **Cloud Computing Platforms:** Distributed systems often run on cloud platforms, like Azure, AWS, or Google Cloud. Understanding how to develop, deploy, and manage applications on these platforms can be a crucial part of distributed development.
6. **Distributed Tracing and Logging:** In a distributed system, being able to trace a transaction or operation across multiple services becomes critical for debugging and performance monitoring. Tools like Serilog, along with services like Azure Application Insights or AWS X-Ray, can help with this.
7. **Resiliency and Fault Tolerance:** In distributed systems, dealing with failures becomes more complex. You may need to implement patterns like Circuit Breaker, Retry, or Fallback to handle potential issues.
8. **Distributed Caching:** In order to reduce latency and increase performance, distributed caching like Redis might be used.
9. **Concurrency and Synchronization:** Dealing with concurrency and synchronization in a distributed environment can be complex, and might involve using locks, semaphores, or other synchronization primitives, and dealing with issues like race conditions and deadlocks.

Keep in mind that distributed development usually involves a lot more than just knowledge of a programming language like C# and a framework like .NET. It includes understanding distributed system principles, various tools, and technologies.

⌂
<br>﹈<br>^1702296738496
 
﹇<br>
What does **cron** stand for?

#card 

<b>C</b>ommand <b>R</b>un <b>O</b><b>N</b>

⌂
<br>﹈<br>^1702296738505

﹇<br>
What is **cron** and what is it used for?

#card 

The `cron` command-line utility is a job scheduler on Unix-like operating systems. Users who set up and maintain software environments use cron to schedule jobs (commands or shell scripts), also known as **cron jobs**, to run periodically at fixed times, dates, or intervals.

It typically automates system maintenance or administration—though its general-purpose nature makes it useful for things like downloading files from the Internet and downloading email at regular intervals.

⌂
<br>﹈<br>^1702296738515

---

## :EiZoteroItem: Bibliography

\[1\]
Microsoft Corporation, .“NET | Build. Test. Deploy.,” _Microsoft_. Available: [https://dotnet.microsoft.com/en-us/](https://dotnet.microsoft.com/en-us/). [Accessed: Dec. 11, 2023]



---

> [!INFO]+ Note
> **Next Note(s)**:
> 

---
