Dependency Inversion Principle

High-level modules should not depend on low-level modules. Both should depend on abstractions.
Abstractions should not depend on details. Details should depend on abstractions.

In the Go context, high-level modules refer to software components that are utilized on top of the application, 
such as presentation code. Understanding it as a layer that provides real business value to our application.
On the other hand,the majority of low-level software components are little code fragments that support 
the higher-level software.They keep technical information regarding various infrastructure integrations hidden.

For example ,This may be a struct that contains the logic for retrieving data from a database, 
sending a SQS message, retrieving a value from Redis, or submitting an HTTP request to an external API. 
So what happens if we break The Dependency Inversion Principle and our high-level component is reliant on a single low-level component?

Have you ever found yourself standing in a shoe store wondering if you should get the brown or the black pair, 
only to get home and regret your choice? Sadly, once you've bought them, they're yours. 
Programming against concrete implementations is the same thing: once you choose, you are stuck with it, 
refunds and refactoring notwithstanding. But why choose when you don't have to? Look 
at the relationship shown in the following diagram:



Not very flexible, is it?  Let's convert the relationship into an abstraction:



That's much better. Everything relies only on nice clean abstractions, satisfying both LSP and ISP. 
The packages are concise and clear, happily satisfying the SRP. The code even seems to 
satisfy Robert C. Martin's description of the DIP, but sadly, it doesn't. It's that pesky word in the middle, inversion. 

In our example, the Shoes package owns the Shoe interface, which is entirely logical. 
However, problems arise when the requirements change. Changes to the Shoes package are 
likely to cause the Shoe interface to want to change. This will, in turn, require the 
Person object to change. Any new features that we add to the Shoe interface may be not be needed or 
relevant to the Person object. Therefore, the Person object is still coupled to the Shoe package.

In order to entirely break this coupling, we need to change the relationship from Person  
uses Shoe to Person  requires Footwear, like this:



There are two key points here. Firstly, the DIP forces us to focus on the ownership of 
the abstractions. In our example, that means moving the interface into the package 
where it was used and changing the relationship from uses to requires; 
it's a subtle difference, but an important one.

Secondly, the DIP encourages us to decouple usage requirements from implementations. 
In our example, our Brown Shoes object implements Footwear, but it's not hard to 
imagine a lot more implementations and some might not even be shoes.
