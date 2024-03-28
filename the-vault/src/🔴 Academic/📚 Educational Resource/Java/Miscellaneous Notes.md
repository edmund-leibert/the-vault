---
title: Miscellaneous Notes
created: 2023-09-03 08:46
updated: 2024-02-19T13:41
authors:
  - Edmund Leibert III
tags:
  - 🔴-academic/📚-educational-resource/name/🗒️-java/🔖/miscellaneous-notes
  - 🔴-academic/📚-educational-resource/format/miscellaneous
  - 🔴-academic/📚-educational-resource/discipline/computer-science/programming-language/java
  - study-note
cards-deck: 🔴 Academic::📚 Educational Resource::🗒️ Java::Miscellaneous Notes
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

In Java, **variable names** should adhere to the following conventions:

- They should start with a lowercase letter.
- If the name contains multiple words, it should be in camelCase. This means the first word is all lowercase, and the first letter of each subsequent word is capitalized. For example, `firstName`, `lastName`.
- Variable names should not start with special characters like `&` (ampersand), `$` (dollar), `_` (underscore).
- One-character variable names should be avoided except for temporary variables.
- Variable names should be meaningful and mnemonic, i.e., designed to indicate to the casual observer the intent of its use.
- Java keywords cannot be used as variable names.

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

These conventions make your code easier to read for yourself and other programmers [@JavaNamingConventions].

⌂
<br>﹈<br>^1707611441293

﹇<br>
As of Feb. 10, 2024 10:58:22 PM, what is a brief summary of the naming conventions of **Java**?

#card 

<table>
	<tr>
		<th>Identifiers</th>
		<th>Naming Rules</th>
		<th>Examples</th>
	</tr>
	<tr>
		<td>Class</td>
		<td>
			<ul>
				<li>It should start with the uppercase letter.</li>
				<li>
					It should be a noun such as: 
					<ul>
						<li>Color</li>
						<li>Button</li>
						<li>System</li>
						<li>Thread</li>
						<li>etc.</li>
					</ul>
				</li>
				<li>Use appropriate words, instead of acronyms.</li>
			</ul>
		</td>
		<td>
			<pre><code class="language-java">public class Employee {
	//code snippet
}</code></pre>
		</td>
	</tr>
	<tr>
		<td>Interface</td>
		<td>
			<ul>
				<li>Use appropriate words, instead of acronyms.</li>
				<li>It should start with the uppercase letter.</li>
				<li>
					It should be an adjective such as: 
					<ul>
						<li>Runnable</li>
						<li>Remote</li>
						<li>ActionListener</li>
					</ul>
				</li>
			</ul>
		</td>
		<td>
			<pre><code class="language-java">interface Printable {
	//code snippet
}</code></pre>
		</td>
	</tr>
	<tr>
		<td>Method</td>
		<td>
			<ul>
				<li>It should start with lowercase letter.</li>
				<li>It should be a verb such as <code>main()</code>, <code>print()</code>, <code>println()</code>.</li>
				<li>If the name contains multiple words, start it with a lowercase letter followed by an uppercase letter such as <code>actionPerformed()</code>.
			</ul>
		</td>
		<td>
			<pre><code class="language-java">class Employee {
	// method
	void draw() {
		//code snippet<br/>
	}<br/>
}</code></pre>
		</td>
	</tr>
	<tr>
		<td>Variable</td>
		<td>
			<ul>
				<li>It should start with a lowercase letter such as id, name, etc.</li>
				<li>It should not start with the special characters like <code>&amp;</code> (ampersand), <code>$</code> (dollar), <code>_</code> (underscore).</li>
				<li>If the name contains multiple words, start it with the lowercase letter followed by an uppercase letter such as firstName, lastName, etc.</li>
				<li>Avoid using one-character variables such as x, y, z.</li>
			</ul>
		</td>
		<td>
			<pre><code class="language-java">class Employee {
	// variable<br/>
	int id;<br/>
	//code snippet<br/>
}</code></pre>
		</td>
	</tr>
	<tr>
		<td>Package</td>
		<td>
			<ul>
			<li>It should be a lowercase letter such as java, lang.</li>
			<li>If the name contains multiple words, it should be separated by dots (<code>.</code>) such as <code>java.util</code>, <code>java.lang</code>.</li>
		</td>
		<td>
			<pre><code class="language-java">//package
package com.javatpoint;
<br/>class Employee {<br/>
	//code snippet<br/>
}</code></pre>
		</td>
	</tr>
	<tr>
		<td>Constant</td>
		<td>
			<ul>
			<li>It should be in uppercase letters such as RED, YELLOW.</li>
			<li>If the name contains multiple words, it should be separated by an underscore(<code>_</code>) such as MAX_PRIORITY.</li>
			<li>It may contain digits but not as the first letter.</li>
		</td>
		<td>
			<pre><code class="language-java">class Employee {<br/>
	//constant<br/>
	static final int MIN\_AGE = 18;
	//code snippet
}</code></pre>
		</td>
	</tr>
</table>

[@JavaNamingConventions]

⌂
<br>﹈<br>^1707635481018


﹇<br>
In software engineering, what is an **interface**? How are interfaces generally implemented in Java?

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

﹇<br>
As of Feb. 11, 2024 12:52:34 AM, what is the `Comparable` interface in Java and what is it used for?

#card 

The `Comparable` interface in Java is used for ordering objects of user-defined classes. A class must implement the `Comparable` interface to allow its instances to be compared to one another. The `Comparable` interface has a single method, `compareTo()`, which is used to define the natural order of the objects.

Here’s an example of how to implement the `Comparable` interface in a class:

```java
import java.util.Arrays;

class Pair implements Comparable<Pair> {
    String x;
    int y;

    public Pair(String x, int y) {
        this.x = x;
        this.y = y;
    }

    @Override
    public int compareTo(Pair a) {
        if (this.x.compareTo(a.x) != 0) {
            return this.x.compareTo(a.x);
        } else {
            return this.y - a.y;
        }
    }

    public String toString() {
        return "(" + x + "," + y + ")";
    }
}

public class Main {
    public static void main(String[] args) {
        Pair[] arr = new Pair[4];
        arr[0] = new Pair("abc", 3);
        arr[1] = new Pair("a", 4);
        arr[2] = new Pair("bc", 5);
        arr[3] = new Pair("a", 2);

        Arrays.sort(arr);
        for (Pair pair : arr) {
            System.out.println(pair);
        }
    }
}
```

In this example, the `Pair` class implements the `Comparable` interface. The `compareTo()` method is overridden to first compare the `String` values (`x`). If they are equal, it then compares the `int` values (`y`). 

The `Arrays.sort()` method is used to sort an array of `Pair` objects.

⌂
<br>﹈<br>


As of Feb. 10, 2024 04:31:30 PM, a 〔1:Java interface〕 only contains 〔1:static constants〕 and 〔1:abstract methods〕.
^1707611622475

As of Feb. 10, 2024 04:29:34 PM, in the context of **Java**, an 〔1:interface〕 is a special type of class that 〔1:only contains abstract methods〕.
^1707611441310

As of Feb. 10, 2024 04:32:55 PM, in the context of **Java**, if a class 〔1:implements an interface but doesn’t provide implementations for all its methods〕, it must be declared as 〔2:abstract〕.
^1707611622480

As of Feb. 10, 2024 04:34:22 PM, the the context of **Java**, the 〔1:`Object`〕 class is the 〔1:superclass for all classes in Java〕.
^1707611754722

﹇<br>
As of Feb. 10, 2024 11:50:13 PM, what is an interface in software engineering?

#card

An interface can be thought of as a contract between the system and the environment. In a computer program, the **system** is the function or module in question, and the **environment** is the rest of the project. 

The interface formally describes what can pass between the system and the environment. It’s a shared boundary across which two or more separate components of a computer system exchange information.  

⌂
<br>﹈<br>^1707612511168

﹇<br>
As of Feb. 10, 2024 11:50:07 PM, what is an interface in Java?

#card

In Java, an interface is a special type of class that only contains abstract methods. It’s a blueprint of a behavior.

A Java interface contains static constants and abstract methods. There can be only abstract methods in the Java interface, not the method body. It is used to achieve abstraction and multiple inheritances in Java.

⌂
<br>﹈<br>^1707612511178

﹇<br>
As of Feb. 10, 2024 11:50:01 PM, how do you implement an interface in Java?

#card

A class implements an interface by using the `implements` keyword followed by the interface name. 

The class must provide implementations for all the methods declared in the interface. If a class implements an interface but **doesn’t** provide implementations for **all** its methods, it must be declared abstract.

⌂
<br>﹈<br>^1707612511182

﹇<br>
As of Feb. 11, 2024 12:04:23 AM, can a Java **interface** include **static** constants?

#card 

Yes, a Java interface can include static constants. In fact, all variables declared in an interface are implicitly `public`, `static`, and `final`. Here’s an example:

```java
public interface Constants {
    int ZERO = 0;
}
```

In this example, `ZERO` is a constant in the `Constants` interface.

However, it’s generally considered not to be a good practice to use interfaces just for defining constants. This is because it can lead to a form of implementation inheritance, which is contrary to the interface’s purpose of defining a contract for behavior. Instead, these constants could be defined in a class or enum where they are most relevant.

⌂
<br>﹈<br>^1707638856708

A Java 〔1:interface can include〕 〔2:static constants〕. In fact, 〔3:all variables declared in an interface〕 are 〔4:implicitly `public`, `static`, and `final`〕.

﹇<br>
As of Feb. 10, 2024 11:49:56 PM, what is the purpose of the `equals()` method in Java?

#card

The `equals()` method is typically used to compare objects for equality. It’s defined in the `Object` class, which is the superclass for all classes in Java. Therefore, all objects in Java inherit this method and can use it to compare for equality.

⌂
<br>﹈<br>^1707612511187

﹇<br>
As of Feb. 11, 2024 12:09:07 AM, in the context of Java, how do you **create** an **interface**?

#card 

In Java, an interface is created using the `interface` keyword. It can include abstract methods (methods without a body) and static constants. Here’s a simple example:

```java
public interface MyInterface {
    // An abstract method
    void myMethod();

    // A static constant
    int MY_CONSTANT = 10;
}
```

In this example, `MyInterface` is an interface that includes an abstract method `myMethod` and a static constant `MY_CONSTANT`.

A class can implement an interface using the `implements` keyword. When a class implements an interface, it needs to provide implementations for all the abstract methods in the interface. Here’s an example:

```java
public class MyClass implements MyInterface {
    @Override
    public void myMethod() {
        // Implementation of myMethod
    }
}
```

In this example, `MyClass` is a class that implements `MyInterface`. It provides an implementation for the `myMethod` abstract method from `MyInterface`.

⌂
<br>﹈<br>^1707639295747

﹇<br>
As of Feb. 11, 2024 12:10:46 AM, what are the **hard** rules that one must keep in mind when trying to **create** an **interface** in **Java**?

#card 

Here are the key rules to keep in mind when creating an interface in Java:

1. **Declaration**: An interface is declared using the `interface` keyword.
2. **Methods**: All methods in an interface are implicitly `public` and `abstract`. This means they do not have a body and must be implemented by any class that uses the interface.
3. **Variables**: All variables declared in an interface are implicitly `public`, `static`, and `final`. This means they are constants.
4. **Implementation**: A class implements an interface using the `implements` keyword. The class must provide implementations for all the methods declared in the interface.
5. **Inheritance**: An interface can extend another interface, just like a class can extend another class.
6. **No Constructors**: Interfaces cannot have constructors. Therefore, you cannot create an instance of an interface.
7. **Multiple Inheritance**: A class can implement multiple interfaces.

Remember, the purpose of an interface is to define a contract for behavior. An interface is not meant to be instantiated itself, but instead is implemented by classes.

⌂
<br>﹈<br>^1707639295755


﹇<br>
As of Feb. 10, 2024 11:49:49 PM, how do you compare primitive types in Java?

#card 

For comparing primitive types, you should use the equality operator `==`. For example, `if (a == b)` would compare two integers `a` and `b`.
^1707612511194

⌂
<br>﹈<br>^1707612511199

﹇<br>
As of Feb. 10, 2024 11:27:50 PM,  does the `equals()` method have the capability to compare primitives?

#card 

The `equals()` method is a feature of objects in Java, not primitive types. Primitive types, such as `int`, `char`, `boolean`, `float`, `double`, `byte`, `short`, and `long`, are not objects and do not have methods.

For comparing primitive types, you should use the equality operator `==`. For example, `if (a == b)` would compare two integers `a` and `b`.

On the other hand, `equals()` is typically used to compare objects for equality. It’s defined in the `Object` class, which is the superclass for all classes in Java. Therefore, all objects in Java inherit this method and can use it to compare for equality.

Here’s an example:

```java
Integer a = new Integer(5);
Integer b = new Integer(5);

if (a.equals(b)) {
    System.out.println("a and b are equal");
} else {
    System.out.println("a and b are not equal");
}
```

In this case, `a` and `b` are `Integer` objects, not `int` primitives, so they can use the `equals()` method.

⌂
<br>﹈<br>^1707636580556

The 〔1:`equals()`〕 method is a feature of 〔2:objects〕 in Java, **not** 〔3:primitive types〕. 〔4:Primitive types〕, such as 〔5:`int`, `char`, `boolean`, `float`, `double`, `byte`, `short`, and `long`〕, are 〔6:not objects and do not have methods〕.
^1707636580561

For 〔1:comparing primitive types〕, you should use the 〔2:equality operator `==`〕. For example, 〔2:`if (a == b)` would compare two integers `a` and `b`〕.
^1707638250449

﹇<br>
As of Feb. 11, 2024 12:17:41 AM, in the context of Java, what is pattern matching?

#card 

In the context of Java, a pattern variable is a local variable that is assigned values extracted from a target only if a certain test, or predicate, is successful.

Pattern variables are introduced in Java as part of the pattern matching feature, which was enhanced in Java 14 with the introduction of the `instanceof` operator. This operator can be used to test if an object is an instance of a certain class, and if the test is successful, the object is automatically cast to that class and assigned to a pattern variable.

Here’s an example of how pattern variables can be used in Java:

```java
if (obj instanceof Savings that) {
    return savingsId.equals(that.savingsId) && amount == that.amount;
}
```

In this example, `that` is a pattern variable. If `obj` is an instance of `Savings`, it is automatically cast to `Savings` and assigned to `that`. The `savingsId` and `amount` of `that` are then accessed directly.

⌂
<br>﹈<br>^1707639763433

﹇<br>
As of Feb. 11, 2024 12:18:39 AM, in the context of Java, specifically the concept of **pattern matching**, why is it necessary to cast an object to the class that was used in checking if the object was instance of that said class?

For better illustration, look at the code below. Why would need to cast the `obj` again to type `Savings` if it is already of type `Savings`?

```java
if (obj instanceof Savings that) {
    return savingsId.equals(that.savingsId) && amount == that.amount;
}
```

#card 

Casting in Java is used to convert an object of one type into another type. In your code, even though you’ve checked that `obj` is an instance of `Savings`, it’s still being treated as an `Object` within the scope of the `equals` method.

The Java compiler doesn’t have the ability to remember the result of the `instanceof` check. So, even though you’ve logically established that `obj` is a `Savings`, as far as the compiler is concerned, `obj` is still an `Object`.

When you try to call a method or access a field that doesn’t exist on `Object` (but does exist on `Savings`), the compiler will give an error. To access the `savingsId` and `amount` fields of `Savings`, you need to cast `obj` to `Savings`.

Here’s the relevant part of your code with comments:

```java
if (!(obj instanceof Savings)) return false;
// At this point, we know obj is a Savings, but it's still being treated as an Object

Savings that;
that = (Savings) obj;  // We cast obj to Savings
// Now that is a Savings, and we can access its fields

return savingsId.equals(that.savingsId) && amount == that.amount;
```

In this code, the casting is necessary to let the compiler know that `obj` should be treated as a `Savings`, not just an `Object`.

⌂
<br>﹈<br>^1707639763440

﹇<br>
As of Feb. 19, 2024 01:38:21 PM, how can I make an `enum` in Java?

#card 

In Java, you can define an `enum` like this:

```java
public enum Day {
    SUNDAY,
    MONDAY,
    TUESDAY,
    WEDNESDAY,
    THURSDAY,
    FRIDAY,
    SATURDAY
}
```

Each of the values (`SUNDAY`, `MONDAY`, etc.) are instances of the `Day` `enum`. You can use them in your code like this:

```java
Day day = Day.MONDAY;

switch(day) {
    case MONDAY:
        System.out.println("Mondays are hard.");
        break;
    case FRIDAY:
        System.out.println("Fridays are better.");
        break;
    // You can have a case for the other days.
    default:
        System.out.println("Midweek days are so-so.");
        break;
}
```

This will print “Mondays are hard.” because `day` is set to `Day.MONDAY`. You can also add methods, fields, and constructors to your `enum` types if needed. Remember that `enum` types are a type of class in Java. They can have methods and fields like any other class, but the list of `enum` values must always come first, and you cannot create new instances of the enum. All instances are automatically created when the `enum` is defined.

⌂
<br>﹈<br>

﹇<br>
As of Feb. 19, 2024 01:39:56 PM, can you add a method to an `enum` in Java?

#card 

Yes, you can add methods to an `enum` in Java. Here’s an example:

```java
public enum Day {
    SUNDAY("Sunday"),
    MONDAY("Monday"),
    TUESDAY("Tuesday"),
    WEDNESDAY("Wednesday"),
    THURSDAY("Thursday"),
    FRIDAY("Friday"),
    SATURDAY("Saturday");

    private final String dayName;

    Day(String dayName) {
        this.dayName = dayName;
    }

    public String getDayName() {
        return this.dayName;
    }
}
```

In this example, each `Day` enum has a `dayName` field and a `getDayName()` method. You can use it like this:

```java
Day day = Day.MONDAY;
System.out.println(day.getDayName());  // This will print "Monday"
```

Remember, the constructor for an `enum` type must be package-private or private access. It automatically creates the constants that are defined at the beginning of the `enum` body. You cannot invoke an `enum` constructor yourself. Also, all fields in an `enum` must be `final` or effectively `final`. They cannot be changed after the `enum` constants are created.

⌂
<br>﹈<br>

﹇<br>
As of Feb. 19, 2024 01:40:44 PM, is it best practice to have an `enum` have a function like `getDayName()` instead of just directly accessing the `enum` itself?

#card 

It depends on the use case. If the `enum` values themselves are sufficient, then you might not need additional methods. However, methods can provide additional functionality and abstraction, which can be beneficial in certain scenarios.

For example, consider an `enum` representing HTTP response status codes. The `enum` values might be `OK`, `NOT_FOUND`, `INTERNAL_SERVER_ERROR`, etc. In this case, you might want a method to get the corresponding status code number (200, 404, 500, etc.). Directly accessing the `enum` value wouldn’t give you this information.

In the `Day` `enum` example, the `getDayName()` method provides a way to get a nicely formatted string representing the day of the week. This could be useful if you’re using the `enum` values in your code but want to display a more user-friendly string in your UI.

So, adding methods to an `enum` in Java can be considered good practice when those methods provide useful functionality that goes beyond what the `enum` values themselves can provide. It’s all about making your code as clear and maintainable as possible. If adding a method to an `enum` helps achieve that, then it’s a good practice. If not, then the method might be unnecessary. It’s always important to consider the specific needs of your project when making these decisions.

⌂
<br>﹈<br>


