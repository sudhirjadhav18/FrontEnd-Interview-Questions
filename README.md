# FrontEnd-Interview-Questions

### General

- What are design patterns in Front End?

There are about 23 different Software Design Patterns that can be grouped into three different categories:

**Creational Pattern:** These are patterns that pertain to object creation and class instantiation they help in the reuse of an existing code. The major creational patterns are Factory Method, Abstract Factory, Builder, Prototype, and Singleton.

**Structural Pattern:** These are patterns that help simplify the design by identifying a way to create relationships among entities such as objects and classes. They are concerned with how classes and objects can be assembled into larger structures. Some of the design patterns that fall into this category are: Adapter, Decorator, and Proxy.

**Behavioral Pattern:** These are patterns that are concerned with responsibilities among objects in order to help increase flexibility in carrying out communication. Some of these patterns are Observer, Memento, and Iterator.

We will look at three different patterns and how to use each of these patterns with TypeScript.

**Singleton:** Singleton is a creational design pattern that lets you ensure that a class has only one instance, while providing a global access point to this instance.
In a Singleton pattern, a class or object can only be instantiated once, and any repeated calls to the object or class will return the same instance. This single instance is what is refered to as a Singleton.

**Observer:** The Observer pattern is pretty common in TypeScript. It specifies a one-to-many relationship between an object and its dependents such that when the object changes state it notifies the other objects that depend on it about the change in state. The observer pattern is also common in the major frontend frameworks and libraries as the whole concept of updating parts of a UI with response to events comes from it.

**Factory Method:** The factory method is a creational pattern that deals with Object creation. It helps in encapsulating an object from the code that depends on it. This might be confusing so let me use an analogy to explain. Imagine having a vehicle plant that produces different vehicles and you start by producing sedans but later on you decide to go into the production of trucks, you’ll probably have to create a duplicate production system for the trucks, now let’s imagine you add SUVs and minivans to the mix. At this point, the production system becomes messy and repetitive.

In a factory pattern, we can abstract the common behavior among the vehicles like how the vehicle is made, into a separate interface object called Vehicle, and then allow the different implementations to implement this common behavior in their unique ways.

### HTML

- How to make *div* horizontally centered align?
- What are web storage?

### CSS

- What is difference between *display:block*, *display:inline* and *display: inline-block*?

**block:** Displays an element as a block element. It starts on a new line and takes up the whole width.<br>
block elements: `div, h1, p, li, section`

**inline:** Displays an element as an inline element. Any height and width properties will have no effect.<br>
inline elements: `span, a, img`

**inline-block:** Displays an element as an inline-level block container. You CAN set height and width values.<br>

- What is Pseudo-class?

Pseudo-class `:hover, :active, ` 
Pseudo-element `::first-letter, ::first-line`

- How to convert square div to circle?

border-radius: 50%;

- What is z-index and why it is used?

### Javascript

- What is DOM?
- What is Closure?
- Write code of any Closure.
- What is Hoisting?
- What is undeclared, undefined and null?
- What is difference between *var, let* and *const*?
- What is deep copy and shallow copy?
- What is event bubbling?
- What is callback hell problem?
- What is difference between array splice and slice?
- Javascript is single threaded or multi-threaded? 
- What is event loop in javascript?

The event loop facilitates this process; it constantly checks whether or not the call stack is empty. If it is empty, new functions are added from the event queue. If it is not, then the current function call is processed.


### Javascript Code

- Find output of below lines if executed in console.log

` 6 = "6" `

` 6 == "6" `
 
` 6 === "6" `
 
` 4<5<6 `
 
` 3>2>1 `

- Write function definition for following calls

` Sum(3, 4); `
 
` Sum(3)(4); `

`function Sum(a, b) {
  return a + b;  
}`

`
function Sum(a){
  return function(b){
    return a + b;
  }
}
`

### Angular

- What are differences in different versions of Angular?

[Follow this link](https://medium.com/@lifenshades/difference-among-angular-8-7-6-5-4-3-2-breakdown-new-features-and-changes-811fb5f8e6f0)

- What are State Management?
- What is Dependency Injection?
- What is Directives?
- What are Services?
- What are Pipes, Pure Pipes, Async Pipes?
- Write code to create Custom Pipes?
- What is interpollation?
- What are different types of databindings?
- What is component harnessing?
- What is tree shaking?
- What is Interceptor?
- How change detection cycle triggers in Angular?
 
Interpolation.<br>
Property binding.<br>
Class binding.<br>
Style binding.<br>
Attribute binding.<br>
Event binding.<br>
Two-way binding.
 
- Write code of Component.
- What is observable, observer, subscribe, subject?
- How to transfer data from Component to Component?
- Can we pass data using router?
- What are Lifecycle hooks?
- What is router states?

RouterState is a tree of activated routes. Every node in this tree knows about the "consumed" URL segments, the extracted parameters, and the resolved data. You can access the current RouterState from anywhere in the application using the Router service and the RouterState property as below.
`
@Component({templateUrl:'template.html'})
class MyComponent {
  constructor(router: Router) {
    const state: RouterState = router.routerState;
    const root: ActivatedRoute = state.root;
    const child = root.firstChild;
    const id: Observable<string> = child.params.map(p => p.id);
    //...
 }
}
`
