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

10. services

A class with specific purpose.

  1. Share data.

  2. Implement common application logic.

  3. External Interaction.

Services club together well defined functionality which can be injected in component. Service should do one kind of functionality and should do it really well.

Services helps to keep components lean and efficient by keeping out the logic except rendering in component classes.
Services helps to maintain the piece of logic which can be injected into any component and is not component specific.

12. Dependancy injection

Dependancy injection is design pattern in which class recieves its dependancies from external sources rather than creating them itself.

Problems without DI
```
class Engine() {
}

class Tires() {
}

class Car() {
 engine;
 tires;
 constructor() {
   this.engine = new Engine()
   this.tires = new Tires()
 }
}
```

If params change, we need to make changes in Car class

Its hard for testing, as for evey instance of Car we will receive same instance of engine and tires, what if we want petrol engines and specific tires.

With DI pattern the dependancies are received from external resource rather that creating them in class itself.

Angular provides injector to manage dependancies,  
Injector registers all the dependancies in angular and provide instance of it whenever called.
Steps for calling service  
  * Define the service.  
  * Register the service with Injector
  * declare the dependancies.

11. Providing services

When you need any service inside the component, injector check for the provider instance if its present injector includes the provider else it creates new instance and add to injector and provides to required class.

By default, when we generate service using ng generate service

Service is register at root level, creating single instance of the serive to be user throgh dependancy injection.

```
@Injectable({
 providedIn: 'root',
})
```

provider helps in making code lean by removing the instance if its not needed in the context.


If we register provicer in NgModule, this will be available across the module for all included components.

```
@NgModule({
  providers: [
  BackendService,
  Logger
 ],
 ...
})
```

If we include providers in component, every component instance will create new instance of the provider.

```
@Component({
  selector:    'app-hero-list',
  templateUrl: './hero-list.component.html',
  providers:  [ HeroService ]
})
```

12. Interpolation

{{ }} which helps in rendering class properties in template.

14. class binding

```
<input [class]="CLASS_NAME" value="v">
<input [class.text_blue]="CONDITION" value="v">
<input [ngClass]="CLASS_OBJECT" value="v">

```

15. Style binding

```
<input [style.color]="'orange'" type="text"/>
<input [style.color]="hasError ? 'orange': ''" type="text"/>
<input [style.color]="variableName" type="text"/>
<input [ngStyle]="variableName" type="text"/>
```

16. DI hierarchy in Angular  
  * If we register service in controller, it will be availabe for that controller and child of that controller.
  * If service is registered in AppController, this will be available in all controllers below App.
  * Service can be registered at NgModule, this will be then available for all the controller in the scope of the project. This is the preferred place to register the service.
  
17. Angular Forms
  * Template Driven Forms:  
  Heavy on component template
  * Reactive / Model driven Forms:  
  Heavy on component class
  
18. Template driven forms
import FormsModule from @angular/forms

Attributes
* ngForm
* ngModel
* ngModelGroup

19. Reactive Forms:
Import ReactiveFormsModule to NgModule
```
import { FormGroup, FormControl } from '@angular/forms';

registrationForm = new FormGroup({ 
  userName: new FormControl(),
  email: new FormControl(),
  address: new FormGroup({
    street: new FormControl()
  });
});

```
FormBuilder services to create forms.

```
import { FormBuilder } from '@angular/forms';

constructor(private fb: FormBilder)

registrationForm = new this.fb.group({ 
  userName: ['DefaultName],
  email: [],
  address: this.fb.group({
    street: []
  });
});
