**JavaScript**

JavaScript is a high-level, often just-in-time compiled language that conforms to the ECMAScript standard.
It has dynamic typing, prototype-based object-orientation, and first-class functions. It is multi-paradigm, 
supporting event-driven, functional, and imperative programming styles. It has application programming interfaces
(APIs) for working with text, dates, regular expressions, standard data structures, and the Document Object Model (DOM).

*JavaScript engine*

A JavaScript engine is a software component that executes JavaScript code. The first JavaScript engines were mere 
interpreters, but all relevant modern engines use just-in-time compilation for improved performance.
JavaScript engines are typically developed by web browser vendors, and every major browser has one. 
In a browser, the JavaScript engine runs in concert with the rendering engine via the Document Object Model.
JavaScript typically relies on a run-time environment (e.g., a web browser) to provide objects and methods by which
scripts can interact with the environment (e.g., a web page DOM). These environments are single-threaded

//TODO adding call, this, bind, etc.
*Object-orientation (prototype-based)*

In JavaScript, an object is an associative array, augmented with a prototype; each key provides the name
for an object property, and there are two syntactical ways to specify such a name: dot notation (obj.x = 10) and
bracket notation (obj['x'] = 10)

JavaScript uses prototypes where many other object-oriented languages use classes for inheritance. It is possible
to simulate many class-based features with prototypes in JavaScript. Every object in JavaScript has a built-in property,
which is called its prototype, all browsers use __proto__ to define prototype variable

    Object.getPrototypeOf(myObject); // Object { }

There are various ways of setting an object's prototype in JavaScript, and here we'll describe two: Object.create() 
and constructors.

  -     Object.create({great(): console.log("hello")})
  -     const personPrototype = { greet() { console.log(`hello, my name is ${this.name}!`); }, };
        function Person(name) { this.name = name; }
        Object.assign(Person.prototype, personPrototype);
        const reuben = new Person("Reuben");
        reuben.greet(); // hello, my name is Reuben!
        console.log(Object.hasOwn(reuben, "name")); //true
        const returnedTarget = Object.assign(target, source); //  copies all enumerable own properties(hasOwn) from one 
                                                              //  or more source objects to a target object

Prefixing a function call with **_new will create an instance of a prototype_**, inheriting properties and methods from 
the constructor (including properties from the Object prototype). Object.create method, allowing explicit creation of an
instance without automatically inheriting from the Object prototype. While it is possible to modify the
Object prototype, it is generally considered bad practice because most objects in JavaScript will inherit methods and
properties from the Object prototype, and they may not expect the prototype to be modified.


**The constructor's prototype property determines the object used for the new object's internal prototype.
New methods can be added by modifying the prototype of the function used as a constructor. JavaScript's built-in
constructors, such as Array or Object, also have prototypes that can be modified.**



*JavaScript APIs*

APIs are ready-made sets of code building blocks that allow a developer to implement programs that would otherwise 
be hard or impossible to implement. They do the same thing for programming that ready-made furniture kits do for home 
building — it is much easier to take ready-cut panels and screw them together to make a bookshelf than it is to work 
out the design yourself, go and find the correct wood, cut all the panels to the right size and shape, find the 
correct-sized screws, and then put them together to make a bookshelf. 


Browser APIs are built into your web browser, and are able to expose data from the surrounding computer environment, 
or do useful complex things. For example:

- The DOM (Document Object Model) API allows you to manipulate HTML and CSS, creating, removing and changing HTML, 
dynamically applying new styles to your page, etc. Every time you see a popup window appear on a page, or some 
new content displayed (as we saw above in our simple demo) for example, that's the DOM in action.

It is bad practice to mix your HTML with JavaScript, and it is inefficient — you'd  have to include the 
onclick="createParagraph()" attribute on every button you want the JavaScript to apply to.Instead of
including JavaScript in your HTML, use a pure JavaScript construct. The querySelectorAll() function allows you to select
all the buttons on a page. You can then loop through the buttons, assigning a handler for each using addEventListener().


**Extra**

First, in class-based OOP, classes and objects are two separate constructs, and objects are always created as instances 
of classes. Also, there is a distinction between the feature used to define a class (the class syntax itself) and the 
feature used to instantiate an object (a constructor). In JavaScript, we can and often do create objects without any 
separate class definition, either using a function or an object literal. This can make working with objects much more 
lightweight than it is in classical OOP.

Second, although a prototype chain looks like an inheritance hierarchy and behaves like it in some ways, it's different 
in others. When a subclass is instantiated, a single object is created which combines properties defined in the subclass
with properties defined further up the hierarchy. With prototyping, each level of the hierarchy is represented by a 
separate object, and they are linked together via the __proto__ property. The prototype chain's behavior is less like 
inheritance and more like delegation. Delegation is a programming pattern where an object, when asked to perform a task,
can perform the task itself or ask another object (its delegate) to perform the task on its behalf. In many ways, 
delegation is a more flexible way of combining objects than inheritance (for one thing, it's possible to change or 
completely replace the delegate at run time).

when instantiate classes, It's worth keeping in mind that the features described by classes are not a new way of 
combining objects: under the hood, they still use prototypes. They're just a way to make it easier to set up a prototype
chain.