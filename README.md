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

NgModules are diffrent than tradiction javascript Modules, In Javascript each js files is a module which contains objects inside which belongs to that modules, some objects are exposed to used by other modules by using export keyword. Other modules can import those object.

6. Angular libraries

Angular loads as collection of Javascript modules, lets think them as library modules. The modules can be load using npm, each  Angular library name begins with @angular. they can be imported using angular import statement.

import { Component } from '@angular/core'

7. 

