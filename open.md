A software artifact should be open for extension but closed for modification.

The Open-Closed Principle (OCP) 

In other words, the behavior of a software artifact ought to be extendible, without having to modify that artifact.

This, of course, is the most fundamental reason that we study software architecture. Clearly, if simple extensions to the requirements force massive changes to the software, then the architects of that software system have engaged in a spectacular failure.

Most students of software design recognize the OCP as a principle that guides them in the design of classes and modules. But the principle takes on even greater significance when we consider the level of architectural components.

A thought experiment will make this clear.

Open means that we should be able to extend or adapt code by adding new behaviors and features. Closed means that we should avoid making changes to existing code, changes that could result in bugs or other kinds of regression.

These two characteristics might seem contradictory, but the missing piece of the puzzle is the scope. When talking about being open, we are talking about the design or structure of the software. From this perspective, being open means that it is easy to add new packages, new interfaces, or new implementations of an existing interface.

When we talk about being closed, we are talking about existing code and minimizing the changes we make to it, particularly the APIs that are used by others. This brings us to the first advantage of OCP:

You can think of OCP as a risk-mitigation strategy. Modifying existing code always has some risk involved, and changes to the code used by others especially so. While we can and should be protecting ourselves from this risk with unit tests, these are restricted to scenarios that we intend and misuses that we can imagine; they will not cover everything our users can come up with.

