@Title: OOP is not what we've been taugh
@PublishDate: 2019-9-23

OOP has had some heavy criticism over the years. It ranges many subjects, from complex and convoluted codebases, to the lack of identity of OOP in general and straight up to false premises of the paradigm. And you can't say that it comes from some conspiracy theorist types. Alan Kay, Edsger Dijkstra and Linus Torvalds are among those people. There's no smoke without fire. It seems though, that much of it doesn't address the OOP paradigm itself, but what it ought to be.

OOP is taught us with principles, states and behaviours. But when experienced developers discuss OOP they talk about types, objects and methods. This adds confusion to newcomers, that often struggle to understand, how what they've taught is related to what they code. In contrast, there's no such disparity in the functional paradigm. What you learn is what you use. How did this happen? Why OOP is described in terms that we rarely use in daily work? And what OOP really is?

## A bit of history

Alan Kay's idea of OOP was vastly different from what's modern OOP represents. He envisioned objects as independent entities that could send messages to each other, akin to living cells. But history took a different turn. Modern OOP was built on other premises. Not on a proper theory, but more on the ideas that floated in the air at the time. You know how it goes, someone makes something smallish for his needs and by luck it becomes wildly popular. For OOP it was the [Simula language](https://en.wikipedia.org/wiki/Simula). Simula was created to describe simulations. Yet somehow we all are now using its derivatives for general purpose programming.

> "I made up the term object-oriented, and I can tell you I did not have C++ in mind."  
> *Alan Kay*

This posed quite a problem. No theory existed on which that new OO paradigm could be based. The paradigm emerged later as extrapolation of developer's experience. This created another problem. What a developer may discover about OOP in his domain may not be true for another. Regardless, the principles of the paradigm were coined: Abstraction, Encapsulation, Inheritance and Polymorphism (I heard rumors, that initially there were only three principles, but couldn't find proves for it). This has created yet another problem: The new paradigm didn't help.

A paradigm is what you default to while coding. In Functional Programming there are rules for you to follow to end up with a robust code. In contrary to what many people believe, once you get used to FP, writing a program is actually a no brainer, even if you are an inexperienced developer. You just flush your thoughts onto the screen, rarely stumbling on complex compositions. This is not so with OOP. The paradigm doesn't give you the answers to how to write your code. There is no method. It only gives you indications of what a good code is: one with good abstractions, that correctly encapsulates implementations by means of inheritance and polymorphism. But how do you get there? And how do you measure it?

It took a decade from the release of the C++ for the [Gang of Four to come up with their book](https://en.wikipedia.org/wiki/Design_Patterns). It came as a revelation to many developers. The impact was so strong, that this book is still one of the most recommended books for developers, more than two decades later. It gives some solutions; yet, it still fails to address the core issue - the lack of method. This has created an additional problem, the one that is dreaded by developers around the world: The Enterprise Code. With no rules to follow, developers took the ones that they were given. The Design Patterns. So they started to stack them on top of each other, because for them the number of patterns per line became both the rule and the measuring tool.

Today we are still at a loss. OOP is taught through the prism of the four foundation principles, which do not aid in understanding of it. And those same principles are used as the base of the OOP criticism that proclaim doom upon its users. And those users ask time and time again to explain them the principles once more. As a bad joke, one of those principles, upon which the whole OOP world is built, is frowned upon, and its usage signifies of inexperience and lack of knowledge. I'm talking about inheritance, of course. How are we still teaching this nonsense?

I believe that, after almost four decades of modern OOP development, we have gained enough knowledge to update the OOP definition. A large amount of experience was acquired through the years. Developers subcountiously use that experience and it was integrated in the modern languages. The last step left is to formalise it.

## What OOP is not

First I would like to make a small breakdown of why OOP principles aren't describing OOP.

### Abstraction

Abstraction is projection of a concept that reveals a subset of the concept needed in current context. As Grady Booch put it:
> "An abstraction denotes the essential characteristics of an object that distinguish it from all other kinds of objects and thus provide crisply defined conceptual boundaries, relative to the perspective of the viewer."

In more simple terms, abstraction allow us to concentrate on the important bits. And it exists everywhere. Monad receives functions and executes them, without knowing anything about what they do. Lambda Calculus relies on abstractions. Turing Machine is an abstraction by itself. Every high-level language can do abstractions. It is not OOP specific.

### Encapsulation

Encapsulation also is part of most modern languages. By encapsulation we can rely only on the interface, without knowing the implementation details. In functional programming every function incapsulates its details exposing only the signature. C header files expose interfaces. Again, not OOP specific.

### Polymorphism

Polymorphism also is encountered in different languages in different forms and variants. Generics, parametric polymorphism, is a part of many modern non-OO languages. JavaScript and Python have duck typing. Functional languages have type classes (which I beleive will soon make their way into OOP languages).

### Inheritance

Without going into much detail, inheritance failed as an OOP principle. The Gang of Four warned us: prefer composition over inheritance.
Even without that warning, Inheritance is only a tool within OOP realm, and some OOP implementations aren't using it, e.g. JavaScript.

You can see that although the OOP principles are a part of OOP paradigm, they are also not unique to it. A paradigm should guide us, light the path toward correct software. It describes a dominant concept that is prevalent in the development. In any situation this is what you default to. OOP doesn't give such guidance. It mainly just sais what a good program is like, not how you get there.

Writing a good program with such a vague definition seems like an impossible feat. No wonder, fresh developers fail at writing a program even slightly more complex than 'Hello World!'. It will take them years of wandering in the dark to get to know their bearings. Because most answers to questions about finding a correct approach to OOP problem boil down to: "It will come with experience." How is one expected to learn from that?

In addition to that, OOP has a whole layer of higher order problems, like leaking state, implicit global state, subtyping limitation, ambiguous decomposition and the whole bunch of others. For this set of problems, another set of principles were created: the SOLID principles. Which also are as vague as it gets.

:::note
*Note: You could argue that languages like Python and JavaScript aren't object oriented. But millions of people that use them claim they are. One can achieve same behaviour of a source code in those and other OO languages. So for all intents and purposes those languages are OO. Anyway, if you are a purist, you have to agree that there is no mainstream object oriented language, since they don't conform to Alan Kay's definition, nor any other unambiguous definition exist.*
:::

## What is OOP?

Comparing toolsets in different languages that describe objects we can interpolate object's common properties:
1. Objects can carry data. This data is commonly called object's state.
2. Objects have methods. Those are functions attached to the object.

There isn't much more, really. All other properties are not universally common and they come and go depending on the used language.

## What is data?

This is quite simple. Data is stored 'within' the object. Holding an object we also hold its data. When object is destroyed, so is the data (in case of references, the reference is destroyed, not necessarily its target). This isn't anything new. There are other types of structures that can do that: structs, unions, records, even functions (lambdas/closures).

The data can have its visibility or mutability limited, which is also nothing new. For functions it is even weirder - the applied data can never be visible nor mutable.

So the data side of the object doesn't have anything special. What about methods?

## What is a method?
First of all, method is a procedure that accepts an instance of the type that is defined on as its first parameter (in many languages this is done implicitly and a keyword like `this` or `self` is used to access object instance). Two questions arise:
1. How is it different from a regular procedure that accepts an instance of the same type?
2. How is it different from a lambda with an applied instance of that type?

Answer to the second question is pretty straightforward. From the user point of view, lambda has no data applied. Accessing the applied instance through the instance of the lambda is not possible. You can't extract the instance for future use or switch it for another one. You are left with only the functionality that is already present in the lambda. It is not possible to change it if the necessity arises.

The first question poses more problems to answer. At the first glance the two seem very similar. The instance of the struct is passed as an argument, and the procedure starts running. Let's examine it closer.

In case of a regular procedure, the call is made by the procedure identifier. That is, this procedure is uniquely identified at compile time. The procedure is found in the heap of all the existing procedures across your codebase. With the arguments loaded onto the stack, the instruction pointer is moved to the start of the procedure, and the procedure is executed.

With an object of a specific type (obviously this only relates to statically typed languages) things work very similar. The procedure is identified by that specific type. Since you know your type at compile time, there can only be one procedure that the identifier can point to. So it is then called like regular procedure.

But when the type of the object is unknown beforehand, things behave very differently. Depending on the language the underlying mechanism will be different, but the outcome is the same: the runtime will look for the procedure that is attached to that specific type on which the method was invoked and execute it. **The resulting procedure will be different based on what was the actual type of the object.**

This gives us first object property: **Objects carry their code with them.**

But that's not all. Examine this code:
```
void Method(object obj)
{
Console.WriteLine(obj.ToString());
}
```

Here, not only you can't deduce what the `ToString` identifier referers to. You also can't know what data the object is holding. Or what this object actually is! Even so, we can still use the object, as long as it complies to the required contract (Interface, type constraint, ad-hoc polymorphism, etc). Since the contract doesn't describe the state of the object, we can't rely on it or even assume whether it exists.

This is the second property: **Object's data (state) is irrelevant.**

## What gives?

Having those two properties in mind, we can now find a productive way of thinking about them. And most importantly describing OOP.

Objects are an abstraction boundary. They achieve that by utilising methods. Unlike static procedures, whose execution is deterministic (unless there's some static state) there is no way to predict what would be an outcome of a method call. Hence, you are abstracted from object's state and method's body. This way objects act similarily to lambdas (in fact, many OOP languages implement lambdas as invocable objects).

Objects own their methods. Having an object at hand means that you not only have some data, but also a code that is used to handle that data. And most importantly, **that code is applicable to that data in its current state**. Given your object is designed correctly, it is not possible to call a method on your object that can't handle the data stored within the object.

This is not so with procedures, where you are free to call any procedure, regardless of object's state. Think of a bank account withdrawal. You are free to call the `withdraw` procedure even if the account is frozen. Then it is up for the procedure the check whether the account isn't frozen. In case of object, the `withdraw` method of the frozen account would just return an error, with no checking whatsoever. Because the object knows, that it's not possible to withdraw money from it.

Based on that property we can conclude that **Objects bring a set of correct procedures into the scope.** They act as a dynamic namespace that is resolved at runtime. With that in mind, it is much easier to reason about the steps you should take next writing your code. Instead of thinking what object structure you need, you can think what things do you want to do.

Since object state may be altered, we can change the implementations of its methods. From simple examples where method returns different values based on its state to more complex solutions where method's code is changed altogether.

Think of it for a bit. There is a very important outcome here: **Object is a tool for runtime metaprogramming.**

As an example think of an object with a `ToString` method. It returns a string based on the object's state. By changing that state, you change the implementation of the method. It may seem silly in such a simple example, but think of a `IDataBaseProvider` for your `Connection` or `IContractResolver` for the serializer. Changing object's state may drastically change the control flow of your program. An object may even change the state of itself, so every consecutive call to its methods would end with different results. If one is not careful, this flexibility will quickly spin out of control.

This is the reason why OOP codebases tend to be very complex and tangled. OOP is easy on the surface. It has not many limitations, and it is easy to start using it. But in fact it is excruciatingly hard. The surface area for introducing bugs is enormous.

In return object give you two important advantages: flexibility and performance. Objects can describe memory layout very closely to the source code, whether you think of data or code. This helps the compiler to better optimize the assembly. And you can change the control flow of the program or any part of it at runtime, without the need of reinitialization.

## Object definition

So now we can finally correctly describe objects:

:::note
Objects are types that have procedure attached to them in form of methods and provide tools for changing the implementations of their methods at runtime.
:::

This definition has several advantages over other that I've encountered throughout the years:
1. It is based on other well established definitions in computer science: type and procedure. Many of the OOP definitions are self-referencing, introduce additional new concepts (Like classes, inheritance, etc) or provide analogies and examples instead.
2. It presents the most prominent feature of the paradigm.
3. It abstracts the implementation details away, thus accounts for different OO flavours.
4. It discourages from using objects where they aren't required. Most types don't need the ability to change method implementations at runtime.

## It's just a tool

OOP may be an absolute beast of an approach. It gives you a great amount of flexibility. But that flexibility is both a blessing and a curse. It may help you elegantly solve most difficult problems, but it will much more easily let you shoot yourself in the foot. There are many problems other paradigms would yield better results.

Given the complexity that OOP brings into the picture, it is a good idea to minimize the object usage and seek for a more simple solutions first. Modern languages allow you to use a wide range of approaches. And when we do use objects, we should opt in OOP features only as necessary, to keep the complexity at a minimum.