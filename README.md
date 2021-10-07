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

### Javascript

- What is DOM?
- What is Closure?
- Write code of any Closure.
- What is Hoisting?
- What is undeclared, undefined and null?
- What is difference between *var, let* and *const*

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

**Angular 2**<br>
Released in 2016<br>
Complete rewrite of Angular 1<br>
Written entirely in typescript<br>
Component-based instead of Controller<br>
ES6 and typescript supported<br>
More testable as component-based<br>
Support for Mobile/Low-end devices<br>
Up to typescript 1.8 is supported

**Angular 4**<br>
Released in 2017<br>
Changes in core library<br>
Angular 4 is simply the next version of angular 2, the underlying concept is the same & is an inheritance from Angular 2<br>
Lot of performance improvement is made to reduce size of AOT compiler generated code<br>
Typescript 2.1 & 2.2 compatible — all feature of ts 2.1 & 2.2 are supported in Angular 4 application<br>
Animation features are separated from @angular/core to @angular/animation<br>
— don’t import` @animation` packages into the application to reduce bundle size and it gives the performance improvement.<br>
Else block in `*ngIf introduced:`<br>
— Instead of writing 2 ngIf for else , simply add below code in component template:<br>
`*ngIf=”yourCondition; else myFalsyTemplate”
“<ng-template #myFalsyTemplate>Else Html</ng-template>”`

**Angular 5**<br>
Released 1st November 2017<br>
Build optimizer: It helps to removed unnecessary code from your application<br>
Angular Universal State Transfer API and DOM Support — By using this feature, we can now share the state of the application between the server side and client side very easily.<br>
Compiler Improvements: This is one of the very nice features of Angular 5, which improved the support of incremental compilation of an application.<br>
Preserve White space: To remove unnecessary new lines, tabs and white spaces we can add below code(decrease bundle size)<br>
// in component decorator you can now add:<br>
`“preserveWhitespaces: false”`<br>
// or in tsconfig.json:<br>
`“angularCompilerOptions”: { “preserveWhitespaces”: false}`<br>
Increased the standardization across all browsers: For internationalization we were depending on `i18n` , but in ng 5 provides a new date, number, and currency pipes which increases the internationalization across all the browsers and eliminates the need of i18n polyfills.<br>
exportAs: In Angular 5, multiple names support for both directives and components<br>
HttpClient: until Angualar 4.3 @angular/HTTP was been used which is now depreciated and in Angular 5 a new module called HttpClientModule is introduced which comes under @angular/common/http package.<br>
Few new Router Life-cycle Events being added in Angular 5: In Angular 5 few new life cycle events being added to the router and those are:<br>
ActivationStart, ActivationEnd, ChildActivationStart, ChildActivationEnd, GuardsCheckStart, GuardsCheckEnd, ResolveStart and ResolveEnd.<br>
Angular 5 supports TypeScript 2.3 version.<br>
Improved in faster Compiler support:<br>
A huge improvement made in an Angular compiler to make the development build faster. We can now take advantage of by running the below command in our development terminal window to make the build faster.<br>
`ng serve/s — aot`

Angular 6
Released on April 2018
This release is focused less on the underlying framework, and more on tool-chain and on making it easier to move quickly with angular in the future
No major breaking changes
Dependency on RxJS 6 (this upgrade have breaking changes but CLI command helps in migrating from older version of RxJS)
Synchronizes major version number of the:
— Angular framework
— Angular CLI
— Angular Material + CDK
All of the above are now version 6.0.0, minor and patch releases though are completely independent and can be changed based on a specific project.
Remove support for <template> tag and “<ng-template>” should be used.
Registering provider: To register new service/provider, we import Service into module and then inject in provider array. e.g:
// app.module.ts
import {MyService} from './my-service';
...
providers: [...MyService]
... 
But after this upgrade you will be able to add providedIn property in injectable decorator. e.g:
// MyService.ts
@Injectable({ providedIn: 'root'})
export class MyService{}
The way ngModelChange event works:
Let’s understand this with output produced by older and this version:
// Angular 5:
<input [(ngModel)]=’name’ (ngModelChange)=’onChange($event)’ />
 onChange(value){ console.log(value); } // Would log updated value
 
<input #modelDir=’ngModel’ [(ngModel)]=’name’ (ngModelChange)=’onChange(modelDir)’ />
 onChange(ngModel: NgModel){ console.log(ngModel.value); } // Would log old value, not updated
// Angular 6:
 onChange(ngModel: NgModel){ console.log(ngModel.value); } // Would log updated value
CLI Changes: Two new commands have been introduced
— ng update <package>
* Analyse package.json and recommend updates to your application
* 3rd parties can provide update scripts using schematics
* automatically update code for breaking changes
* staying update and low maintenance
— ng add
* add new capablities to your applicaiton
* e.g ng add @angular/material : behind the scene it add bit of necessary code and changes project where needed to add it the thing we just told it to add.
* Now adding things like angular material, progressive web app, service workers & angular elements to your existing ng application will be easy.
CLI + Material starter templates: Let angular create code snippet for your basic components. e.g:
— Material Sidenav
* ng generate @angular/material:material-nav — name=my-nav
Generate a starter template including a toolbar with app name and then the side navigation & it's also responsive
— Dashboard
* ng generate @angular/material:material-dashboard — name=my-dashboard
Generates Dynamic list of cards
— Datatable
* ng generate @angular/material:material-table — name=my-table
Generates Data Table with sorting, filtering & pagination
It uses angular.json instead of .angular-cli.json
Support for multiple projects: Now in angular.json we can add multiple projects
initial release of Angular Elements which gives us ability to use our angular components in other environments like a Vue.js application. Its potential is truly amazing but unfortunately this release only works for angular application, we need to wait for next release to wrap out angular component into custom element and use it with framework like Vue.js
Angular 7:
Released on October 2018
This is a major release and expanding to the entire platform including-
— Core framework,
— Angular Material,
— CLI
CLI Prompts: The CLI will now prompt users as when running common commands likeng new or ng add @angular/material with the intend of getting aid for building a new project using SCSS.
Added a new interface — UrlSegment[] to CanLoad interface
Added a new interface — DoBootstrap interface
Angular 7 added a new compiler — Compatibility Compiler (ngcc)
Introduce a new Pipe called — KeyValuePipe
Angular 7 now supporting to TypeScript 2.9.
Added a new elements features — enable Shadow DOM v1 and slots
Added a new router features — warn if navigation triggered outside Angular zone
Added a new mapping for ngfactory and ngsummary files to their module names in AOT summary resolver.
Added a new “original” placeholder value on extracted XMB
Added a new ability to recover from malformed URLs
Added a new compiler support dot (.) in import statements and also avoid a crash in ngc-wrapped
Update compiler to flatten nested template fns
Angular 8:
Releasing March/April 2019
Being smaller, faster and easier to use and it will be making Angular developers life easier.
Added Support for TypeScript 3.2
Added a Navigation Type Available during Navigation in the Router
Added pathParamsOrQueryParamsChange mode for runGuardsAndResolvers in the Router
Allow passing state to routerLink Directives in the Router
Allow passing state to NavigationExtras in the Router
Restore the whole object when navigating back to a page managed by Angular Router
Added support for SASS
Resolve generated Sass/Less files to .css inputs
Added Predicate function mode for runGuardsAndResolvers:-
This option means guards and resolvers will ignore changes when a provided predicate function returns `false`. This supports use cases where an application needs to ignore some param updates but not others. For example, changing a sort param in the URL might need to be ignored, whereas changing the `project` param might require a re-run of guards and resolvers.
Added functionality to mark a control and its descendant controls as touched: — add markAllAsTouched () to AbstractControl
Added an ng-new command that builds the project with Bazel
Use image based cache for windows BuildKite
Export NumberValueAccessor & RangeValueAccessor directives
Use shared DomElementSchemaRegistry instance for improve performance of platform-server(@angular/platform-server):-
Right now the ServerRendererFactory2 creates a new instance of the DomElementSchemaRegistry for each and every request, which is quite costly (for the Tour of Heroes SSR example this takes around **15%** of the overall execution time)
Now the Performance Improvements on the core, more consistent about “typeof checks”: -
When testing whether `value` is an object, use the ideal sequence of strictly not equal to `null` followed by `typeof value === ‘object’` consistently. Specifically, there’s no point in using double equal with `null` since `undefined` is ruled out by the `typeof` check. Also avoid the unnecessary ToBoolean check on `value.ngOnDestroy` in `hasOnDestroy()`, since the `typeof value.ngOnDestroy === ‘function’` will only let closures pass and all closures are truish (with the notable exception of `document.all`, but that shouldn’t be relevant for the `ngOnDestroy` hook)
In the Compiler-CLI, expose ngtsc as a TscPlugin
Restore whole object when navigating back to a page managed by Angular Router:-
This feature adds a few capabilities. First, when a `popstate` event fires the value of `history.state` will be read and passed into `NavigationStart`. In the past, only the `navigationId` would be passed here.
Additionally, `NavigationExtras` has a new public API called `state` which is any object that will be stored as a value in `history.state` on navigation. For example, the object `{foo: ‘bar’}` will be written to `history.state` here: -`router.navigateByUrl(‘/simple’, {state: {foo: ‘bar’}});`

- What are State Management?
- What is Dependency Injection?
- What are Services?
- What are Pipes?
- Write code to create Custom Pipes?
- What is interpollation?
- What are different types of databindings?
- Write code of Component.
- What is observable?
- How to transfer data from Component to Component?
- Can we pass data using router?
