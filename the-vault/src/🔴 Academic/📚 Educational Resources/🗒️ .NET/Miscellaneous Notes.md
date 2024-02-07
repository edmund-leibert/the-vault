---
title: Miscellaneous Notes
created: 2023-09-03 08:46
updated: 2024-02-04T14:22
authors:
  - Edmund Leibert III
tags:
  - 🔴-academic/📚-educational-resources/name/🗒️-net/🔖/miscellaneous-notes
  - 🔴-academic/📚-educational-resources/format/miscellaneous
  - 🔴-academic/📚-educational-resources/discipline/computer-science/developer-platform/net
  - study-note
cards-deck: 🔴 Academic::📚 Educational Resources::🗒️ .NET::Miscellaneous Notes
banner: "![[https://i.imgur.com/ZLk5l96.jpg]]"
banner_y: 0
---

# Miscellaneous Notes

---

> [!INFO]+ Note 
> This **page** contains **miscellaneous** _scratch notes_ pertaining to **[.NET](https://dotnet.microsoft.com/en-us/)** [@NETBuildTest].
> 
> These notes are primarily structured in a Q&A format, making it easy to follow and learn. Corresponding [**Anki**](https://apps.ankiweb.net/) flashcards are available, enabling efficient revision and reinforcement of the concepts [@ankitectsAnkiPowerfulIntelligent].

---

> [!INFO]+ Note
> **Previous Notes**:
> 

---

﹇<br>
In brief, what is Microsoft’s **.NET**?

#card 

**.NET** is a free, cross-platform, [open-source developer platform](https://github.com/dotnet/core) for building [many kinds of applications](https://learn.microsoft.com/en-us/dotnet/core/apps). It can run programs written in [multiple languages](https://learn.microsoft.com/en-us/dotnet/fundamentals/languages), with [C#](https://learn.microsoft.com/en-us/dotnet/csharp/) being the most popular. It relies on a [high-performance](https://devblogs.microsoft.com/dotnet/category/performance/) runtime that is used in production by many [high-scale apps](https://devblogs.microsoft.com/dotnet/category/developer-stories/) [@genevievewarrenIntroductionNETNET2024].

⌂
<br>﹈<br>^1707085375786


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
<br>﹈<br>^1707085375799


﹇<br>
Using the [DocTo](https://github.com/tobya/DocTo) library, how can I export a `.docx` to a `.pdf` in the command line [@tobyallenDocToXLSTo]?

#card #🔴-academic/📚-educational-resources/discipline/computer-science/technologies/docto

```pwsh
docto -f C:\Directory\MyFile.doc -O "C:\Output Directory\MyTextFile.pdf" -T wdFormatPDF
```

⌂
<br>﹈<br>^1702296738200

﹇<br>
What does JSON stand for?

#card #🔴-academic/📚-educational-resources/discipline/computer-science/technology/json

**J**ava**S**cript **O**bject **N**otation

⌂
<br>﹈<br>^1702296738213

﹇<br>
What _namespace_ in **.NET** provides functionality for _serializing_ to and _deserializing_ form **J**ava**S**cript **O**bject **N**otation (JSON)?

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

[In C#, and generally in most programming languages, serialization does **not** include an object’s methods](https://stackoverflow.com/questions/2767893/are-methods-also-serialized-along-with-the-data-members-in-net) [@lisaAreMethodsAlso2010] [@ramezaniWhatMeaningSerialization2020]. [Serialization is the process of converting the state of an object into a form that can be persisted or transported](https://learn.microsoft.com/en-us/dotnet/standard/serialization/) [@genevievewarrenSerializationNET2023] [@naeemSerializationDeserialization2023]. [The serialized form includes only the data members (fields and properties) of the object](https://stackoverflow.com/questions/2767893/are-methods-also-serialized-along-with-the-data-members-in-net) [@lisaAreMethodsAlso2010] [@ramezaniWhatMeaningSerialization2020].

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

As you can see, the serialized JSON string includes the values of the `Name` and `Age` properties, but it does not include any information about the `GetGreeting()` method. [This is because serialization is about capturing the state (data) of an object, not its behavior (methods)](https://stackoverflow.com/questions/2767893/are-methods-also-serialized-along-with-the-data-members-in-net) [@lisaAreMethodsAlso2010] [@ramezaniWhatMeaningSerialization2020].

⌂
<br>﹈<br>^1702296738231

﹇<br>
In the context of software engineering, specifically** .NET**, is it possible to also _serialize_ an object's _methods_. If not, how do we rebuild an object with its methods when _deserializing_ data?

#card #🔴-academic/📚-educational-resources/discipline/computer-science/programming-language/csharp 

[In .NET, serialization is the process of converting the state of an object into a form that can be persisted or transported](https://learn.microsoft.com/en-us/dotnet/standard/serialization/) [@genevievewarrenSerializationNET2023]. This typically includes the values of its properties. [However, the serialized form **does not include any information about an object’s associated methods**](https://learn.microsoft.com/en-us/dotnet/standard/serialization/system-text-json/overview) [@genevievewarrenSerializeDeserializeJSON2023].

[When you deserialize, you reconstruct an object from the serialized form](https://learn.microsoft.com/en-us/dotnet/standard/serialization/) [@genevievewarrenSerializationNET2023]. The deserialization process does not automatically rebuild the methods of an object. [Instead, the methods are part of the class definition, and when an object is deserialized, it is an instance of that class with its state (i.e., field values) populated from the serialized data](https://learn.microsoft.com/en-us/dotnet/standard/serialization/system-text-json/overview) [@genevievewarrenSerializeDeserializeJSON2023].

If you need to call methods on a deserialized object, those methods should be part of the class definition. When you deserialize an instance of the class, you can call any public methods defined in the class.

Here’s a simple example of serialization and deserialization using `System.Text.Json`:

```csharp
public class UserData
{
    public int UserId { get; set; }

    // This method is not serialized
    public string GetUserIdString()
    {
        return $"User ID: {UserId}";
    }
}

// Serialization
var userData = new UserData { UserId = 0 };
var userDataString = System.Text.Json.JsonSerializer.Serialize(userData);

// Deserialization
var deserializedUserData = System.Text.Json.JsonSerializer.Deserialize<UserData>(userDataString);

// Now you can call the method on the deserialized object
string userIdString = deserializedUserData.GetUserIdString();
```

[In this example, the `GetUserIdString` method is not serialized, but after deserialization, you can call it on the `deserializedUserData` object because it’s part of the `UserData` class definition](https://learn.microsoft.com/en-us/dotnet/standard/serialization/) [@genevievewarrenSerializationNET2023] [@dotnet-botJsonSerializerSerializeMethod].

If you need to modify the behavior of methods after deserialization based on the serialized data, consider using a design pattern such as the Strategy pattern, where the serialized data determines which implementation of a method to use. Another approach could be to include some kind of configuration data in your serialized object that your methods can use to alter their behavior after deserialization. However, these approaches go beyond basic serialization and deserialization and involve more advanced object-oriented design.

⌂
<br>﹈<br>^1707085375806


﹇<br>
In general, what is the definition of *serialization*?

#card-reverse #🔴-academic/📚-educational-resources/discipline/computer-science/programming-language/csharp 

[<span class="spoiler">**Serialization**</span> is the process of translating a data structure or object state into a format that can be stored (e.g., in files or data buffers) or transmitted (e.g., over computer networks) and reconstructed later, possibly in a different computer environment](https://en.wikipedia.org/wiki/Serialization) [@Serialization2023] [@WhatSerialization2022] [@baeldungWhatAreSerialization2023]. [This process allows us to save the data associated with an object and recreate the object in a new location](https://en.wikipedia.org/wiki/Serialization) [@baeldungWhatAreSerialization2023]. [The serialized form does not include any information about an object’s associated methods](https://en.wikipedia.org/wiki/Serialization) [@Serialization2023].

Here’s a simple example of serialization in C#:

```csharp
// An object to be serialized
var userData = new UserData { UserId = 0 };

// Serialization
var userDataString = System.Text.Json.JsonSerializer.Serialize(userData);
```

⌂
<br>﹈<br>^1702296738238

﹇<br>
What is the definition of *deserialization*?

#card-reverse #🔴-academic/📚-educational-resources/discipline/computer-science/programming-language/csharp 

<span class="spoiler">**Deserialization**</span> is the reverse process of serialization. [It involves taking data structured in some format and rebuilding it into an object](https://en.wikipedia.org/wiki/Serialization) [@theowaspfoundationDeserializationOWASPCheat] [@dagsterlabsDataDeserializationDagster]. [This process is used to extract the data or the state of the object from the stored or received serialized format](https://en.wikipedia.org/wiki/Serialization) [@dagsterlabsDataDeserializationDagster].

Here’s a simple example of deserialization in C#:

```csharp
// Deserialization
var deserializedUserData = System.Text.Json.JsonSerializer.Deserialize<UserData>(userDataString);
```

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

Sure, let’s break down these terms:

- **.NET Framework**: This is the original .NET platform introduced by Microsoft in 2002. [It’s a platform for developing Windows-based applications using languages such as C# and VB.NET](https://www.c-sharpcorner.com/article/comparing-net-framework-net-core-net-5-and-net-6/) [@keyurComparingNETFramework]. [It includes a common runtime environment called the Common Language Runtime (CLR) and a set of class libraries and APIs that support various functionalities](https://www.c-sharpcorner.com/article/comparing-net-framework-net-core-net-5-and-net-6/) [@keyurComparingNETFramework].
- [**.NET Core**: Introduced by Microsoft in 2016, .NET Core is a cross-platform, open-source alternative to .NET Framework](https://www.c-sharpcorner.com/article/comparing-net-framework-net-core-net-5-and-net-6/) [@keyurComparingNETFramework]. [It can run on Linux and macOS as well as Windows](https://www.c-sharpcorner.com/article/comparing-net-framework-net-core-net-5-and-net-6/) [@keyurComparingNETFramework]. [It’s modular and lightweight, allowing developers to choose only the components they need for their applications](https://www.c-sharpcorner.com/article/comparing-net-framework-net-core-net-5-and-net-6/) [@keyurComparingNETFramework]. [It also offers improved performance and scalability compared to .NET Framework](https://www.c-sharpcorner.com/article/comparing-net-framework-net-core-net-5-and-net-6/) [@keyurComparingNETFramework].
- [**.NET**: In 2020, Microsoft released .NET 5 as the next major version of .NET Core](https://www.c-sharpcorner.com/article/comparing-net-framework-net-core-net-5-and-net-6/) [@keyurComparingNETFramework]. [It’s intended to be the single platform for all types of .NET development, whether it’s Windows-based or cross-platform](https://www.c-sharpcorner.com/article/comparing-net-framework-net-core-net-5-and-net-6/) [@keyurComparingNETFramework]. [It merges the best features and capabilities of both .NET Core and .NET Framework while also adding new ones](https://www.c-sharpcorner.com/article/comparing-net-framework-net-core-net-5-and-net-6/) [@keyurComparingNETFramework].
- [**ASP.NET**: This is a framework for building web applications that runs on .NET](https://stackoverflow.com/questions/44136118/net-core-vs-asp-net-core) [@blubberboNETCoreVs2020]. [ASP.NET Core is a version of ASP.NET that runs on both .NET Core and .NET 5.0, on top of multiple OS platforms: Windows, Linux & macOS](https://stackoverflow.com/questions/44136118/net-core-vs-asp-net-core) [@blubberboNETCoreVs2020]. [ASP.NET 4.x (ASP.NET/ASP.NET MVC) runs on the .NET Framework only, on top of Windows OS](https://stackoverflow.com/questions/44136118/net-core-vs-asp-net-core)  [@blubberboNETCoreVs2020].

[In summary, .NET Framework is the original platform for Windows development, .NET Core is a cross-platform alternative, .NET is the unified platform for all .NET development, and ASP.NET is a framework for building web applications that can run on .NET Framework, .NET Core, or .NET](https://learn.microsoft.com/en-us/dotnet/standard/choosing-core-framework-server) [@genevievewarrenChooseNETNET2022] [@keyurComparingNETFramework]  [@blubberboNETCoreVs2020].

⌂
<br>﹈<br>^1702296738273

﹇<br>
As of 2024, can **.NET** be considered a newer version of **.NET Core**?

#card 

Yes, that’s correct. **.NET 5** and its successors are the next step forward from **.NET Core**.

Microsoft merged the best of .NET Core and .NET Framework into a single platform called .NET. This unified platform is intended to be used for all types of .NET development, whether it’s Windows-based or cross-platform. So, you can think of .NET as a newer version of .NET Core.

⌂
<br>﹈<br>^1707085375820


﹇<br>
In the context of .NET, what does **IIS** stand for and what is it?

#card #🔴-academic/📚-educational-resources/discipline/computer-science/technology/

IIS stands for **I**nternet **I**nformation **S**ervices. [It is a flexible, secure, and manageable web server for hosting web applications, including ASP.NET Core](https://learn.microsoft.com/en-us/aspnet/core/host-and-deploy/iis/?view=aspnetcore-8.0) [@rickandersonHostASPNET2023].

[An IIS web server runs on the Microsoft .NET platform on the Windows OS](https://stackify.com/iis-web-server/) [@vuolletWhatIISWeb2023]. [While it’s possible to run IIS on Linux and Macs using Mono, it’s not recommended and will likely be unstable](https://stackify.com/iis-web-server/) [@vuolletWhatIISWeb2023]. [It’s versatile and stable, and it’s been widely used in production for many years](https://stackify.com/iis-web-server/) [@vuolletWhatIISWeb2023].

Most commonly, IIS is used to host ASP.NET web applications and static websites. [It can also be used as an FTP server, host WCF services, and be extended to host web applications built on other platforms such as PHP](https://stackify.com/iis-web-server/) [@vuolletWhatIISWeb2023].

[In the context of ASP.NET, IIS allows web applications to fully leverage the powerful features and extensibility of ASP.NET](https://learn.microsoft.com/en-us/aspnet/core/host-and-deploy/iis/?view=aspnetcore-8.0) [@leanserverIISWebServer2022]. [Features including forms-based authentication, membership, session state, and many others can be used for all types of content, providing a unified experience across the entire web application](https://learn.microsoft.com/en-us/iis/get-started/introduction-to-iis/iis-web-server-overview) [@leanserverIISWebServer2022].

⌂
<br>﹈<br>^1702296738281

﹇<br>
As of 2024, is **IIS** current out “outdated”? If it is outdated, what is a modern alternative to it currently?

#card

[**Internet Information Services (IIS)** is still being used and supported by Microsoft](https://learn.microsoft.com/en-us/lifecycle/products/internet-information-services-iis) [@leanserverIISWebServer2022]. [However, it’s important to note that older versions of IIS (7.5 and below) are no longer supported by Microsoft and may be vulnerable to attacks](https://cybernews.com/security/millions-of-microsoft-web-servers-powered-by-vulnerable-legacy-software/) [@edvardasmikalauskasMillionsMicrosoftWeb2023]. [Therefore, it’s recommended to use the latest version of IIS for the most secure and best performance](https://learn.microsoft.com/en-us/lifecycle/products/internet-information-services-iis) [@leanserverIISWebServer2022].

As for alternatives to IIS, there are several modern web servers that you might consider:

- [**NGINX**: An open-source web server that is known for its high performance, stability, rich feature set, simple configuration, and low resource consumption](https://www.trustradius.com/products/iis/competitors) [@trustradiusListBestMicrosoft] [@alternativetoMicrosoftIISAlternatives2019].
- **Apache HTTP Server**: An open-source web server that’s been a popular choice for many years. [It’s highly configurable and supports a range of features](https://www.trustradius.com/products/iis/competitors) [@trustradiusListBestMicrosoft] [@alternativetoMicrosoftIISAlternatives2019].
- [**Caddy**: A powerful, enterprise-ready, open-source web server with automatic HTTPS written in Go](https://alternativeto.net/software/microsoft-iis/) [@alternativetoMicrosoftIISAlternatives2019].
- [**LiteSpeed**: Known for its speed, this is a drop-in Apache replacement and the 4th most popular web server on the internet](https://designpress.com/web-development/lightweight-alternatives-to-apache-and-iis-web-servers/) [@dimmittLightweightAlternativesApache2011].
- [**Lighttpd**: A secure, fast, compliant, and very flexible web-server that has been optimized for high-performance environments](https://designpress.com/web-development/lightweight-alternatives-to-apache-and-iis-web-servers/) [@dimmittLightweightAlternativesApache2011].

[Each of these servers has its own strengths and weaknesses, and the best one for you depends on your specific needs and circumstances](https://www.trustradius.com/products/iis/competitors) [@trustradiusListBestMicrosoft] [@alternativetoMicrosoftIISAlternatives2019] [@dimmittLightweightAlternativesApache2011]. [It’s also worth noting that while these alternatives can serve as replacements for IIS, they might not offer the same level of integration with other Microsoft technologies](https://www.trustradius.com/products/iis/competitors) [@trustradiusListBestMicrosoft] [@alternativetoMicrosoftIISAlternatives2019] [@dimmittLightweightAlternativesApache2011].

⌂
<br>﹈<br>^1707085375830

﹇<br>
Just to clarify, what server am I running when I run a simple **Node.js** application locally? In your explanation, make sure to relate this to how Microsoft’s **IIS** works too?

#card 

[When you run a JavaScript Node.js application locally, you’re typically running it on a **Node.js server**](https://stackoverflow.com/questions/5489956/how-could-others-on-a-local-network-access-my-nodejs-app-while-its-running-on)[1](https://stackoverflow.com/questions/5489956/how-could-others-on-a-local-network-access-my-nodejs-app-while-its-running-on)[2](https://sabe.io/tutorials/setting-up-local-web-server-node-js)[3](https://stackoverflow.com/questions/6084360/using-node-js-as-a-simple-web-server). [Node.js includes a built-in HTTP server library, allowing you to run a web server without the use of external software](https://stackoverflow.com/questions/5489956/how-could-others-on-a-local-network-access-my-nodejs-app-while-its-running-on)[1](https://stackoverflow.com/questions/5489956/how-could-others-on-a-local-network-access-my-nodejs-app-while-its-running-on)[2](https://sabe.io/tutorials/setting-up-local-web-server-node-js)[3](https://stackoverflow.com/questions/6084360/using-node-js-as-a-simple-web-server).

[For example, if you’re using the `http-server` package in Node.js, you’re running a simple, zero-configuration HTTP server that serves up static files](https://sabe.io/tutorials/setting-up-local-web-server-node-js)[2](https://sabe.io/tutorials/setting-up-local-web-server-node-js). [You can start this server with a command like `http-server` in your project directory](https://stackoverflow.com/questions/6084360/using-node-js-as-a-simple-web-server)[3](https://stackoverflow.com/questions/6084360/using-node-js-as-a-simple-web-server).

Now, let’s talk about **IIS (Internet Information Services)**. [IIS is a web server software created by Microsoft for use with the Windows operating system](https://www.hanselman.com/blog/installing-and-running-nodejs-applications-within-iis-on-windows-are-you-mad)[4](https://www.hanselman.com/blog/installing-and-running-nodejs-applications-within-iis-on-windows-are-you-mad)[5](https://devtut.github.io/nodejs/using-iisnode-to-host-node-js-web-apps-in-iis.html). [It’s used to host websites and other content on the web](https://www.hanselman.com/blog/installing-and-running-nodejs-applications-within-iis-on-windows-are-you-mad)[4](https://www.hanselman.com/blog/installing-and-running-nodejs-applications-within-iis-on-windows-are-you-mad)[5](https://devtut.github.io/nodejs/using-iisnode-to-host-node-js-web-apps-in-iis.html).

[In terms of Node.js, you can actually run your Node.js applications on IIS using the **iisnode** module](https://stackoverflow.com/questions/5489956/how-could-others-on-a-local-network-access-my-nodejs-app-while-its-running-on)[4](https://www.hanselman.com/blog/installing-and-running-nodejs-applications-within-iis-on-windows-are-you-mad)[6](https://stackoverflow.com/questions/46266609/host-node-js-on-windows-server-iis)[7](https://adrianjnkns.medium.com/iis-hosting-nodejs-application-572d81689f9e). [The iisnode module allows hosting of Node.js applications in IIS on Windows](https://stackoverflow.com/questions/5489956/how-could-others-on-a-local-network-access-my-nodejs-app-while-its-running-on)[4](https://www.hanselman.com/blog/installing-and-running-nodejs-applications-within-iis-on-windows-are-you-mad)[6](https://stackoverflow.com/questions/46266609/host-node-js-on-windows-server-iis)[7](https://adrianjnkns.medium.com/iis-hosting-nodejs-application-572d81689f9e). [This can be beneficial if you’re already using IIS for other applications and want to keep everything on the same server](https://stackoverflow.com/questions/5489956/how-could-others-on-a-local-network-access-my-nodejs-app-while-its-running-on)[4](https://www.hanselman.com/blog/installing-and-running-nodejs-applications-within-iis-on-windows-are-you-mad)[6](https://stackoverflow.com/questions/46266609/host-node-js-on-windows-server-iis)[7](https://adrianjnkns.medium.com/iis-hosting-nodejs-application-572d81689f9e).

However, it’s important to note that running a Node.js application on IIS is not the same as running it on a Node.js server. When you run your Node.js application locally without IIS, you’re running it directly on a Node.js server. [When you run it on IIS using iisnode, IIS is acting as a reverse proxy, forwarding requests to your Node.js application and then returning the responses](https://www.hanselman.com/blog/installing-and-running-nodejs-applications-within-iis-on-windows-are-you-mad)[4](https://www.hanselman.com/blog/installing-and-running-nodejs-applications-within-iis-on-windows-are-you-mad)[6](https://stackoverflow.com/questions/46266609/host-node-js-on-windows-server-iis)[7](https://adrianjnkns.medium.com/iis-hosting-nodejs-application-572d81689f9e).

⌂
<br>﹈<br>^1707085375836


﹇<br>
What are HTTP, HTTP/2, HTTPS, FTP, FTPS, SMTP and NNTP?

#card 

These are all network protocols. They are designed to send/transfer information over a computer network and are a integral part of today’s internet.

⌂
<br>﹈<br>^1702296738290

﹇<br>
In the context of software engineering, specifically in the language **C#** (**.NET**), what exactly is an `async` function and how does it work? Relate your description/analysis to threads at the operating system level.

#card #🔴-academic/📚-educational-resources/discipline/computer-science/programming-language/csharp 

[In C#, an `async` function is a method, lambda expression, or anonymous method that is marked with the `async` keyword](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/async)[1](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/async)[2](https://www.c-sharpcorner.com/article/async-and-await-in-c-sharp/). [This keyword indicates that the function is asynchronous, meaning it can run in the background while other code executes](https://stackify.com/c-threading-and-multithreading-a-guide-with-examples/)[3](https://stackify.com/c-threading-and-multithreading-a-guide-with-examples/).

Here’s how it works:

1. [An `async` method runs synchronously until it reaches its first `await` expression](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/async)[1](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/async). [The `await` keyword is used to specify that the method should wait for the result of an asynchronous operation before continuing](https://www.c-sharpcorner.com/article/async-and-await-in-c-sharp/)[2](https://www.c-sharpcorner.com/article/async-and-await-in-c-sharp/).
2. [At the `await` expression, the method is suspended, and control returns to the caller of the method](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/async)[1](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/async). [This allows the application to continue with other work that doesn’t depend on the awaited task](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/task-asynchronous-programming-model)[4](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/task-asynchronous-programming-model).
3. [Once the awaited task is complete, the method resumes where it left off](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/async)[1](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/async).

In terms of threads at the operating system level, here’s the relationship:

- [The `async` and `await` keywords don’t cause additional threads to be created](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/async)[5](https://stackoverflow.com/questions/37278281/async-await-and-threads). [They work with the .NET runtime to handle the asynchronicity](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/async)[6](https://auth0.com/blog/introduction-to-async-programming-in-csharp/).
- When an `async` method awaits a task, it frees up its thread to do other work. [This could be the UI thread, allowing the application to remain responsive](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/async)[4](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/task-asynchronous-programming-model).
- [For I/O-bound code, you `await` an operation that returns a `Task` or `Task<T>` inside of an `async` method](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/async)[4](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/task-asynchronous-programming-model). [For CPU-bound code, you `await` an operation that is started on a background thread with the `Task.Run` method](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/async)[7](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/async-scenarios).

Here’s a simple example of an `async` function in C#:

```csharp
public async Task<int> ExampleMethodAsync()
{
    // This method runs asynchronously.
    int result = await SomeOtherAsyncMethod();
    return result;
}
```

In this example, `ExampleMethodAsync` is an `async` method that returns a `Task<int>`. Inside the method, it calls `SomeOtherAsyncMethod()` and `await`s its result. Once `SomeOtherAsyncMethod()` completes, its result is returned from `ExampleMethodAsync`.

⌂
<br>﹈<br>^1707085375845

﹇<br>
Two brief questions: 
1. When calling an `async` method, must you have an `await` prepended/before it when calling it? 
2. Must an `async` method, by definition, must call another `async` function?

#card #🔴-academic/📚-educational-resources/discipline/computer-science/programming-language/csharp 

1. **Do you need to use `await` when calling an `async` method?**
    - [No, it’s not mandatory to use `await` when calling an `async` method](https://stackoverflow.com/questions/15522900/how-to-safely-call-an-async-method-in-c-sharp-without-await)[1](https://stackoverflow.com/questions/15522900/how-to-safely-call-an-async-method-in-c-sharp-without-await)[2](https://stackoverflow.com/questions/17805887/using-async-without-await). [However, if you call an `async` method without `await`, the method will return a `Task` or `Task<T>` immediately, and the caller will continue execution before the `async` method has completed](https://stackoverflow.com/questions/15522900/how-to-safely-call-an-async-method-in-c-sharp-without-await)[1](https://stackoverflow.com/questions/15522900/how-to-safely-call-an-async-method-in-c-sharp-without-await)[2](https://stackoverflow.com/questions/17805887/using-async-without-await). [This can lead to unexpected behavior if the caller depends on the completion of the `async` method](https://stackoverflow.com/questions/15522900/how-to-safely-call-an-async-method-in-c-sharp-without-await)[1](https://stackoverflow.com/questions/15522900/how-to-safely-call-an-async-method-in-c-sharp-without-await)[2](https://stackoverflow.com/questions/17805887/using-async-without-await). [If you don’t need to wait for the `async` method to complete, you can ignore the returned `Task`](https://stackoverflow.com/questions/15522900/how-to-safely-call-an-async-method-in-c-sharp-without-await)[1](https://stackoverflow.com/questions/15522900/how-to-safely-call-an-async-method-in-c-sharp-without-await)[2](https://stackoverflow.com/questions/17805887/using-async-without-await). [But be aware that any exceptions thrown by the `async` method will be swallowed and won’t be observed until the `Task` is awaited](https://stackoverflow.com/questions/15522900/how-to-safely-call-an-async-method-in-c-sharp-without-await)[1](https://stackoverflow.com/questions/15522900/how-to-safely-call-an-async-method-in-c-sharp-without-await).
2. **Does an `async` function have to call another `async` function?**
    - Not necessarily. [An `async` method doesn’t have to call another `async` method](https://stackoverflow.com/questions/9343594/how-to-call-asynchronous-method-from-synchronous-method-in-c)[3](https://stackoverflow.com/questions/9343594/how-to-call-asynchronous-method-from-synchronous-method-in-c)[4](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/async-scenarios). [However, if an `async` method doesn’t contain an `await` expression, it will run synchronously](https://stackoverflow.com/questions/15522900/how-to-safely-call-an-async-method-in-c-sharp-without-await)[3](https://stackoverflow.com/questions/9343594/how-to-call-asynchronous-method-from-synchronous-method-in-c)[4](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/async-scenarios). [That means the method will execute on the same thread and won’t yield control back to the caller until it’s completed](https://stackoverflow.com/questions/15522900/how-to-safely-call-an-async-method-in-c-sharp-without-await)[3](https://stackoverflow.com/questions/9343594/how-to-call-asynchronous-method-from-synchronous-method-in-c)[4](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/async-scenarios). [This can defeat the purpose of making the method `async` in the first place](https://stackoverflow.com/questions/15522900/how-to-safely-call-an-async-method-in-c-sharp-without-await)[3](https://stackoverflow.com/questions/9343594/how-to-call-asynchronous-method-from-synchronous-method-in-c)[4](https://learn.microsoft.com/en-us/dotnet/csharp/asynchronous-programming/async-scenarios).

⌂
<br>﹈<br>^1707085375850

﹇<br>
It seems unless I specify manually the creation of extra threads in **C#**, when an `async` method is now waiting (via `await`) for another method to finish execution and return a task, the threads itself don't change or go off the processor, but instead the thread itself switches to execute a different method. Is this correct?

#card #🔴-academic/📚-educational-resources/discipline/computer-science/programming-language/csharp 

In C#, when an `async` method encounters an `await` keyword, it doesn’t necessarily create a new thread. Instead, it signs up the rest of the method as a continuation on the awaited task. The thread that was executing the method can then go back to the thread pool and be used for another work until the awaited task completes. When the awaited task completes, the continuation (the rest of the method) can be executed on a different thread.

This is one of the key benefits of `async`/`await` in C# - it allows you to write asynchronous code that can free up threads to do other work, without manually creating and managing threads. This can lead to more efficient use of system resources, particularly in I/O-bound operations.

⌂
<br>﹈<br>^1707085375854


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

#card #🔴-academic/📚-educational-resources/discipline/computer-science/programming-language/csharp 

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

[1]
Microsoft Corporation, .“NET | Build. Test. Deploy.,” _Microsoft_. Available: [https://dotnet.microsoft.com/en-us/](https://dotnet.microsoft.com/en-us/). [Accessed: Dec. 11, 2023]

[2]
“Introduction to .NET - .NET,” _Microsoft Learn: Build skills that open doors in your career_, Jan. 10, 2024. Available: [https://learn.microsoft.com/en-us/dotnet/core/introduction](https://learn.microsoft.com/en-us/dotnet/core/introduction). [Accessed: Jan. 30, 2024]

[3]
Toby Allen, “DocTo & XLSTo,” _DocTo & XLSTo | DocTo_. Available: [http://tobya.github.io/DocTo/](http://tobya.github.io/DocTo/). [Accessed: Jan. 30, 2024]

[4]
dotnet-bot, “System.Text.Json Namespace,” _Microsoft Learn: Build skills that open doors in your career_. Available: [https://learn.microsoft.com/en-us/dotnet/api/system.text.json?view=net-8.0](https://learn.microsoft.com/en-us/dotnet/api/system.text.json?view=net-8.0). [Accessed: Jan. 31, 2024]

[5]
“How to serialize JSON in C# - .NET,” _Microsoft Learn: Build skills that open doors in your career_, Oct. 25, 2023. Available: [https://learn.microsoft.com/en-us/dotnet/standard/serialization/system-text-json/how-to](https://learn.microsoft.com/en-us/dotnet/standard/serialization/system-text-json/how-to). [Accessed: Jan. 31, 2024]

[6]
Lisa, “Are methods also serialized along with the data members in .NET?,” _Stack Overflow_, May 05, 2010. Available: [https://stackoverflow.com/q/2767893/8088657](https://stackoverflow.com/q/2767893/8088657). [Accessed: Feb. 01, 2024]

[7]
masoud ramezani, “What is the meaning of serialization in programming languages?,” _Stack Overflow_, Apr. 24, 2020. Available: [https://stackoverflow.com/q/3042665/8088657](https://stackoverflow.com/q/3042665/8088657). [Accessed: Feb. 01, 2024]

[8]
“Serialization in .NET,” _Microsoft Learn: Build skills that open doors in your career_, Oct. 25, 2023. Available: [https://learn.microsoft.com/en-us/dotnet/standard/serialization/](https://learn.microsoft.com/en-us/dotnet/standard/serialization/). [Accessed: Feb. 01, 2024]

[9]
F. Naeem, “Serialization and Deserialization in C#,” _C# Corner - Community of Software and Data Developers_, Jun. 15, 2023. Available: [https://www.c-sharpcorner.com/article/serialization-and-deserialization-in-c-sharp/](https://www.c-sharpcorner.com/article/serialization-and-deserialization-in-c-sharp/). [Accessed: Feb. 01, 2024]

[10]
“Serialize and deserialize JSON using C# - .NET,” _Microsoft Learn: Build skills that open doors in your career_, Oct. 25, 2023. Available: [https://learn.microsoft.com/en-us/dotnet/standard/serialization/system-text-json/overview](https://learn.microsoft.com/en-us/dotnet/standard/serialization/system-text-json/overview). [Accessed: Feb. 01, 2024]

[11]
dotnet-bot, “JsonSerializer.Serialize Method (System.Text.Json),” _Microsoft Learn: Build skills that open doors in your career_. Available: [https://learn.microsoft.com/en-us/dotnet/api/system.text.json.jsonserializer.serialize?view=net-8.0](https://learn.microsoft.com/en-us/dotnet/api/system.text.json.jsonserializer.serialize?view=net-8.0). [Accessed: Feb. 01, 2024]

[12]
“Serialization,” _Wikipedia, the free encyclopedia_. Oct. 01, 2023. Available: [https://en.wikipedia.org/w/index.php?title=Serialization&oldid=1178142559](https://en.wikipedia.org/w/index.php?title=Serialization&oldid=1178142559). [Accessed: Feb. 01, 2024]

[13]
“What is Serialization?,” _freeCodeCamp.org_, Jan. 10, 2022. Available: [https://www.freecodecamp.org/news/what-is-serialization/](https://www.freecodecamp.org/news/what-is-serialization/). [Accessed: Feb. 01, 2024]

[14]
baeldung, “What Are Serialization and Deserialization in Programming? | Baeldung on Computer Science,” _Baeldung on CS_, Jun. 17, 2023. Available: [https://www.baeldung.com/cs/serialization-deserialization](https://www.baeldung.com/cs/serialization-deserialization). [Accessed: Feb. 01, 2024]

[15]
The OWASP Foundation, “Deserialization - OWASP Cheat Sheet Series,” _OWASP Cheat Sheet Series_. Available: [https://cheatsheetseries.owasp.org/cheatsheets/Deserialization_Cheat_Sheet.html](https://cheatsheetseries.owasp.org/cheatsheets/Deserialization_Cheat_Sheet.html). [Accessed: Feb. 01, 2024]

[16]
Dagster Labs, “Data Deserialization | Dagster Glossary,” _Dagster | Cloud-native orchestration of data pipelines_. Available: [https://dagster.io/glossary/data-deserialization](https://dagster.io/glossary/data-deserialization). [Accessed: Feb. 01, 2024]

[17]
Keyur, “Comparing .NET Framework, .NET Core, .NET 5, and .NET 6,” _C# Corner - Community of Software and Data Developers_. Available: [https://www.c-sharpcorner.com/article/comparing-net-framework-net-core-net-5-and-net-6/](https://www.c-sharpcorner.com/article/comparing-net-framework-net-core-net-5-and-net-6/). [Accessed: Feb. 01, 2024]

[18]
blubberbo, .“NET Core vs ASP.NET Core,” _Stack Overflow_, Feb. 26, 2020. Available: [https://stackoverflow.com/q/44136118/8088657](https://stackoverflow.com/q/44136118/8088657). [Accessed: Feb. 01, 2024]

[19]
Genevieve Warren, “Choose between .NET and .NET Framework for server apps - .NET,” _Microsoft Learn: Build skills that open doors in your career_, Oct. 04, 2022. Available: [https://learn.microsoft.com/en-us/dotnet/standard/choosing-core-framework-server](https://learn.microsoft.com/en-us/dotnet/standard/choosing-core-framework-server). [Accessed: Feb. 01, 2024]

[20]
Rick Anderson, “Host ASP.NET Core on Windows with IIS,” _Microsoft Learn: Build skills that open doors in your career_, Jul. 11, 2023. Available: [https://learn.microsoft.com/en-us/aspnet/core/host-and-deploy/iis/?view=aspnetcore-8.0](https://learn.microsoft.com/en-us/aspnet/core/host-and-deploy/iis/?view=aspnetcore-8.0). [Accessed: Feb. 01, 2024]

[21]
P. Vuollet, “What is IIS Web Server: (Internet Information Services)?,” _Stackify_, Sep. 27, 2023. Available: [https://stackify.com/iis-web-server/](https://stackify.com/iis-web-server/). [Accessed: Feb. 01, 2024]

[22]
leanserver, “IIS Web Server Overview,” _Microsoft Learn: Build skills that open doors in your career_, Aug. 23, 2022. Available: [https://learn.microsoft.com/en-us/iis/get-started/introduction-to-iis/iis-web-server-overview](https://learn.microsoft.com/en-us/iis/get-started/introduction-to-iis/iis-web-server-overview). [Accessed: Feb. 01, 2024]

---

> [!INFO]+ Note
> **Next Notes**:
> 

---
