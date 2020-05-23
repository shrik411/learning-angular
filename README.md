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

