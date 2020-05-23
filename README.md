# learning-angular
1. What is NgModule

NgModules are containers for a cohesive block of code dedicated to an application domain, a workflow, or a closely related set of capabilities. 

2. More on NgModule
Ng module is cohensive block of code, dedicated to and application domain. a workflow or a closely related set of capabilities.
defined with @NgModule decorator which contains
declarations: component, decorators and pipes
exports: declaration for other modules to be used.
imports: Other modules declarations, to be used in current module
providers: services, these are application level declarations, we can define provider in components which is preferred way.
bootstrat: This is used to define the root component, used only in app module/ root module.

4. Component

Component and templates together makes view in angular, NgModule declaration contains the list of components needed in the context.
Typical component contains hierarchy of other components which can be part of same module or exported from other modules to form structure at the time of rendering.
Hierarchy is very important in angular rendering as this bring a view by hidding and showing diffrent components depending on DOM or programme data changes.

5. NgModules and JavaScript modules

NgModules are diffrent
than tradiction javascript Modules, In Javascript each js files is a module which contains objects inside which belongs to that modules, some objects are exposed to used by other modules by using export keyword. Other modules can import those object.

6. Angular libraries

Angular loads as collection of Javascript modules, lets think them as library modules. The modules can be load using npm, each  Angular library name begins with @angular. they can be imported using angular import statement.

import { Component } from '@angular/core'

7. Components 

Components control patch of screen called view

For example, individual components define and control each of the following views from the Tour of Heroes tutorial:

The app root with the navigation links.
The list of heroes.
The hero editor.

8. Pipes, directive and data binding

Pipes transform HTML data before it is displayed, directive insert app logic before it gets displayed. template use data binding to coordinate between app logic and DOM data.
Pipes transform display values and directives help to transform DOM elements according to instructions given by directives.

9. Directives

Angular tempalates are dynamic, Directives provides way to transform the dom according to the logic defined in directives.
@Componet is a type of directive. However, in angular component is so distict and central to the application that angular defines @Component decorator which is derived from @Directive decorator with metadata elements to specify HTML template.

Types of Directives

1. Component

Apart from Component which contains metadata to specify which HTML template to render, other direcitves are places as the attributes in HTML elements.

2. Structural

Structural directive is something which makes changes in DOM before rendering depending on the logic defined in Directive. This render, update or destroy the DOM element depending on the property values. ex:- *ngFor, *ngSwitch, *ngIf

3. Attribute

Attribute directives alter appearance or behaviour of the DOM element. ex:- <input [(ngModule)]="hero.name"/>




