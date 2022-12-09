1. Software Engineering Process

The software engineering process comes with a set of guidance, education, and discipline which can be predictable. 
The engineering steps for each product will be the same but the time spent on each level will be different 
as per the team size and project goals. Basically, software engineering is a method that is used for the development 
of software solutions from the scratch.

The steps of this process are –

- Requirement Analysis
- Software Designing
- Creating Source Code
- Testing the System
- Post-deployment Maintenance

Basically, there are many software engineering process models and they vary as per the application, frequency, and implementation. 
Today we will just focus on 12 of the software principles.

2. Top Software Engineering Principles

Some of the top principles of software development are –

2.1 DRY (Don’t Repeat Yourself)

When the developer is writing a code, it is essential that he doesn’t repeat himself. 
Andy Hunt and Dave Thomas’ book The Pragmatic Programmer: From Journeyman to Master was the first to introduce this principle. 
This means that he has to avoid copy-pasting the code in various places in the program. In simple words, 
each piece of data should have a single source of truth (SSOT). This is primarily due to the necessity to further modify and maintain the code. 
This helps in solving future maintenance issues. If the developer doesn’t follow this rule, he will have to make changes 
to the coding in different places at later stages. And those changes will demand more changes when the system goes under testing. 
And this will take more effort, time, and money.

The following are some software engineering techniques that are based on the DRY principle:

Inheritance and Composition
Inheritance and composition both allow you to write code once and then reuse it anywhere else.

Database Normalization
Database normalization is a database design approach that eliminates data redundancy. In simple words, it avoids the repetition of data.

Therefore, it is advisable to extract common logic into different functions but not copy the same code.

2.2 You Aren’t Gonna Need It (YAGNI).  
YAGNI is derived from a software development methodology called Extreme Programming (XP). 
Mostly all the software developers try to implement all the features and functionalities at once in the system and this is where the issue starts. 
For adding all the features at once, the programmer adds code that isn’t even necessary or that is not going to be useful 
in the near future and this makes the code be present in the system even if it isn’t required. So as per the YAGNI principle, 
if any such method or feature has been added, it must be removed while refactoring the system so that the developers can add 
useful features when the system starts taking a proper shape.

This principle is known as YAGNI. It helps in saving a lot of costs, time, and effort that goes behind understanding or debugging the code.

2.5 Avoid Premature Optimization

Generally, developers prefer to write code that is easy to maintain and understand. And because of this, 
the programmers might want to over-optimize the source code and make it faster. Optimized code can also use less memory. 
But in the case of premature optimization, the code can waste a lot of time. The reason behind it is that the developers 
avoid seeing what is actually happening. They optimize the code pre-maturely but it doesn’t turn out well as it is not perfectly ready.

So if the code is not perfectly ready and the programmer is not sure about the exact problem in the code, 
premature optimization is not an optimal approach.

2.6 Big Design Up Front (BDUF)

BDUF is a software engineering principle that confirms that a software developer completes the design of the project first and then implements it. 
This principle helps in discovering various issues at the requirement stage and solving it. But the changes in the software requirements 
that occur during the process can cause difficulties. Therefore, having a general architecture first before developing a functionality is very important. 
It enables setting priorities.

2.7 Dynamic Systems Development Method (DSDM)

DSDM (dynamic systems development method) is one of the most important principles when it comes to software development. 
It comes with three main factors that can be fixed beforehand. These three factors are known as time, cost, and quality. 
Besides this, the dynamic systems development method is something that embraces the MoSCoW prioritization approach for priority modification. 
And doing this results in timely delivery.

2.8 Fail Fast

Another principle of the software development process is “fail fast”. It is the most preferred approach by Silicon Valley. 
As per this concept, the software must crash if any error occurs. In this way, if any new programmers check the variable 
for a 0 or null value and try to continue the code even when it is not possible, an error should be shown by causing a crash. 
In the world of project management, this principle is known as a technical barrier that might come at the beginning stage of the project.

2.9 Occam’s Razor

William Occam, a philosopher of the 14th came up with a principle- “Entities are not to be multiplied without necessity” 
which was known as Occam’s Razor. As per this concept, one must select the hypotheses that have the fewest assumption. 
And to keep up with the lean software development process, the developer must always start the code with straightforwardness. 
And later on, they can add some complex modules such as method, class, tool, process or etc if needed. The main reason behind 
it is that the simple code enables easy development, testing, and correction of the product. In addition to this, 
it also helps in significantly reducing bugs.

2.12 Demeter

The Demeter principle states that the responsibilities of the software must be divided between classes and reduce coupling.
By following this principle the developers can keep the entities of the software independent of each other. It also enables 
in reduction of the coupling or communication between different classes. 
Besides, the Demeter principle also puts related classes into the same module to achieve cohesion.

2.13 Avoid trying to reinvent the wheel.  
Don’t spend your time bother to build solutions that already exist and are available. 
All modern programming takes place in the object-oriented model and you can easily find design patterns, free libraries, ready-made modules, 
and API-based solutions that can accelerate your project.


2.14 Degrade gracefully.  
Graceful degradation means that even if there is an error or an incident while the program is being executed, 
the software should continue running smoothly instead of just shutting down. 
If it just shut down, your users could lose their data or changes which they made - and that’s something you can’t have happening.

2.15 Data Protection.  
It is critical for data to be protected from unauthorized access. 
For that reason, secure software development life-cycle principles need to be applied and propagated throughout the entire software structure. 

2.16 Measure Twice and Cut Once.  
The development life cycle’s requirement stage usually introduces more than 50% coding issues if not done well. 
Therefore, be prepared by developing a systematic approach to the coding process.
Double-check all the project’s requirements to ensure you don’t leave out or add too much in your code. 
After that, make blueprints that will guide the whole process to achieve high-quality coding throughout. 
Always test your project from the word go to ensure everything is fine.
This principle gives much more predictable outcomes, especially if the project’s cost is already high. 
You’ll save yourself headaches that come with deleting or adding code lines to meet requirements.

2.17 Refactoring.  
Refactoring is all about  bringing improvements to internal software structure without having any effect on its behavior or functions. Refactoring is an integral part of the perpetual 
software maintenance process and it involves frequently reviewing and improving the code to make it lighter and more powerful.

2.18 Minimum viable product (MVP)

When creating something new, it is best to have it do the least it can do really well rather than have it do everything 
it *could* do but not quite as well. That’s called the minimum viable product (MVP).

Doing the MVP makes it easier to demonstrate the utility to a user or customer. 
And there is less to correct if it is wrong, and less invested if it fails.

1.19  Beware race conditions

Generally, a race condition is the multithreaded violation of a design by contract.

In its simplest form: If two threads are modifying the same variable and if one thread does it first, things are fine. But if the second thread modifies the variable first, you have an error—that is a race condition.

It isn't always possible to detect these sorts of design flaws. There is no unit test that can catch them because frequently they are intermittent and occur only under load. Heavily defensive design and avoiding cooperation among threads are good ways to prevent race conditions. Still, even with messaging and event-driven software, there are other versions of race conditions that are possible (just less likely). Concurrency is just hard.

2.20 Test first

In a modern IDE, you should test first. That means to write a unit test first and then have it generate your classes and such. This results in higher quality software because it makes highly testable software. It also tends to cause you to follow other design principles, like design by contract.

