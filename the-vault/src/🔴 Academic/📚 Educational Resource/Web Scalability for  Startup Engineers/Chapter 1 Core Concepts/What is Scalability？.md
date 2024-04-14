---
title: What is Scalability?
created: 2024-04-12T05:58
updated: 2024-04-13T22:28
authors:
  - Edmund Leibert III
tags:
  - 🔴-academic/📚-educational-resource/name/web-scalability-for-startup-engineers/🔖/chapter-1-core-concepts/what-is-scalability？
  - 🔴-academic/📚-educational-resource/format/book
  - 🔴-academic/📚-educational-resource/discipline/computer-science
  - study-note
cards-deck: 🔴 Academic::📚 Educational resource::Web Scalability for Startup Engineers::Chapter 1 Core Concepts::What is Scalability?
banner: 
banner_y: 
---

# What is Scalability?

---

> [!NOTE] Note
> These notes are of the **“What is Scalability?”** section of the **“Chapter 1. Core Concepts”** of the _**Web Scalability for Startup Engineers**_ book.
>  
> These notes are structured in a Q&A format, making it easy to follow and learn. Corresponding Anki flashcards are available, enabling efficient revision and reinforcement of the concepts. [@ejsmontWebScalabilityStartup2015]
> 

---

> [!NOTE] Note
> **Previous Notes**:
> 

---

> [!NOTE] Note
> 
> **<ins>Table of Contents</ins>**
> 
> :TiNotes: [What is Scalability?](obsidian://open?vault=the-vault&file=the-vault%2Fsrc%2F%F0%9F%94%B4%20Academic%2F%F0%9F%93%9A%20Educational%20resource%2FWeb%20Scalability%20for%20%20Startup%20Engineers%2FChapter%201.%20Core%20Concepts%2FWhat%20is%20Scalability%EF%BC%9F)
> - Evolution from a Single Server to a Global Audience
> - Overview of a Data Center Infrastructure
> - Overview of the Application Architecture
> - Summary
>

---

> [!NOTE] Note 
> :EiZotero: Page 3
>
> > Scalability is an ability to adjust the capacity of the system to cost- efficiently fulfill the demands. Scalability usually means an ability to handle more users, clients, data, transactions, or requests without affecting the user experience. It is important to remember that scalability should allow us to scale down as much as scale up and that scaling should be relatively cheap and quick to do.
>
> ---
> What is the definition of scalability?
> ^IYDYUYB5aKJZ5LZHZp24
> 

﹇<br>
As of Apr. 12, 2024 08:59:56 AM, what is **scalability** and its importance in a system?

#card 

Scalability is the ability to adjust the capacity of a system to cost-efficiently fulfill demands. It usually means the ability to handle more users, clients, data, transactions, or requests without affecting the user experience. Importantly, scalability should allow us to scale down as much as scale up, and scaling should be relatively cheap and quick to do.

⌂
<br>﹈<br>

 Scalability should allow us to 〔1:scale down〕 〔2:as much as〕 〔1:scale up〕, and 〔1:scaling〕 should be 〔2:relatively cheap and quick to do〕.


﹇<br>
As of Apr. 12, 2024 11:26:00 AM, what are the common challenges of handling more data in terms of scalability?

#card 

As a business grows and becomes more popular, it will have to handle more user accounts, products, location data, and digital content. 

Processing more data puts pressure on the system as data needs to be sorted, searched through, read from disks, written to disks, and sent over the network. 

Especially today, with the growing popularity of big data analytics, companies are storing ever-growing amounts of data without ever deleting it.

⌂
<br>﹈<br>

﹇<br>
As of Apr. 12, 2024 11:26:04 AM, what does handling higher concurrency levels mean in terms of scalability?

#card 

Concurrency measures how many clients your system can serve at the same time. If you are building a web-based application, concurrency means how many users can use your application at the same time without affecting their user experience. 

Concurrency is difficult, as your servers have a limited amount of central processing units (CPUs) and execution threads. It is even more difficult, as you may need to synchronize parallel execution of your code to ensure consistency of your data. 

Higher concurrency means more open connections, more active threads, more messages being processed at the same time, and more CPU context switches.

⌂
<br>﹈<br>

﹇<br>
As of Apr. 12, 2024 11:26:07 AM, what does handling higher interaction rates mean in terms of scalability?

#card 

The third dimension of scalability is the rate of interactions between your system and your clients. It is related to concurrency, but is a slightly different dimension. The rate of interactions measures how often your clients exchange information with your servers. For example, if you are building a website, your clients would navigate from one page to another, triggering server requests.

⌂
<br>﹈<br>

﹇<br>
As of Apr. 12, 2024 11:27:53 AM, what are the three measurements used for scalability?

#card 

1. **Handling more data**: This involves efficiently managing an increasing amount of user accounts, products, location data, and digital content.
2. **Handling higher concurrency levels**: This measures how many clients your system can serve at the same time without affecting the user experience.
3. **Handling higher interaction rates**: This measures how often your clients exchange information with your servers.

⌂
<br>﹈<br>^1713056580295


Got it, I will use the current time when creating Anki style flashcards going forward. Here are the cards with the time updated to 9:10:23 PM:

﹇<br>
As of Apr. 12, 2024 09:10:23 PM, what is concurrency?

#card

Concurrency measures how many clients your system can serve at the same time. If you are building a web-based application, concurrency means how many users can use your application at the same time without affecting their user experience.

⌂
<br>﹈<br>^1713056580310


> [!NOTE]  
> Page 3
> 
>  > concurrency
> 
> ---
> How is concurrency and parallelism related?
> ^YNY8965FaKJZ5LZHZp24
> 

> [!NOTE] 
> Page 3
> 
>  > Concurrency measures how many clients your system can serve at the same time.
> 
> ---
> The definition of concurrency.
> ^DWLVAHDDaKJZ5LZHZp24
> 

﹇<br>
As of Apr. 12, 2024 09:10:23 PM, why is **concurrency** difficult?

#card

Concurrency is difficult, as your servers have a limited amount of central processing units (CPUs) and execution threads. It is even more difficult, as you may need to synchronize parallel execution of your code to ensure consistency of your data.

⌂
<br>﹈<br>^1713056580315


﹇<br>
As of Apr. 12, 2024 09:10:23 PM, what does higher concurrency mean?  

#card

Higher concurrency means more open connections, more active threads, more messages being processed at the same time, and more CPU context switches.

⌂
<br>﹈<br>

﹇<br>
As of Apr. 12, 2024 09:19:08 PM, what is the difference between **concurrency** and **parallelism**?

#card

**Parallelism** utilizes multiple CPU cores to execute multiple threads entirely simultaneously. For example, if you have a multi-core processor, it can do multiple calculations at exactly the same time, with each calculation running on a separate CPU core.

**Concurrency** is about dealing with multiple tasks in a way that allows them to make progress by interleaving their execution on a single CPU core. For example, a web server handles multiple requests concurrently by switching between servicing one request at a time when it is waiting on I/O for another request.

At a lower level, concurrency is about structuring your program and using techniques like async/await, callbacks, promises, threads, etc. to allow separate tasks to be interleaved. Parallelism requires parallel hardware and distributes different segments of the same task across multiple CPU cores.

⌂
<br>﹈<br>

﹇<br>
As of Apr. 12, 2024 09:22:03 PM, how are parallelism and concurrency related?

#card

**Parallelism** and **concurrency** are closely related concepts, but with some key differences:

**Parallelism** is about truly doing multiple tasks at the exact same time, by utilizing multiple CPU cores. Concurrency is about dealing with multiple tasks in a way that allows them to make progress independently and be interleaved on a single CPU core.

However, **concurrency** enables parallelism on a multi-core system. By breaking tasks down into independently executable units, concurrent programs can effectively utilize multiple cores for parallel execution.

So while parallelism requires multiple CPUs/cores, concurrency is a program structure and technique that allows a single process to be divided into tasks that can execute in parallel once CPU cores are available.

> [!IMPORTANT] Important
> **Concurrency** is a broader concept that encompasses parallelism on systems with multiple CPUs/cores, but allows programs to still make progress on single-core systems.
> 

⌂
<br>﹈<br>

---

## :EiZoteroItem: Bibliography

\[1\]
A. Ejsmont, _Web Scalability for Startup Engineers_. New York: McGraw-Hill Education, 2015.

---

> [!NOTE] Note
> **Next Notes**:
> - [0. Introduction ∋ Folder Note](the-vault/src/🔴%20Academic/📚%20Educational%20Resource/Structy/0.%20Introduction/0.%20Introduction%20∋%20Folder%20Note.md)

---
