# Filters and their type in MRC

In an MVC (Model-View-Controller) application in .NET, filters are used to intercept and modify the behavior of controller action methods and other components of the application. Filters are a powerful feature of MVC that can be used to implement cross-cutting concerns, such as logging, security, caching, and performance optimization, in a modular and reusable way.

There are several different types of filters in MVC, each of which is applied at a different stage of the request processing pipeline. Here are the most common types of filters:

1. Authorization filters: Authorization filters are used to control access to controller action methods and other components of the application. They can be used to enforce security policies, such as requiring users to be authenticated before accessing certain parts of the application.
    
2. Action filters: Action filters are used to modify the behavior of individual controller action methods. They can be used to implement cross-cutting concerns, such as logging, caching, or performance optimization, that affect the behavior of multiple action methods.
    
3. Result filters: Result filters are used to modify the result returned by a controller action method or other components of the application. They can be used to implement cross-cutting concerns, such as adding headers to the response or modifying the content of the response.
    
4. Exception filters: Exception filters are used to handle exceptions that occur during the processing of a request. They can be used to implement cross-cutting concerns, such as logging errors or returning a custom error page to the user.
    
5. Resource filters: Resource filters are used to modify the resources used by a controller action method or other components of the application. They can be used to implement cross-cutting concerns, such as localization or resource compression, that affect the behavior of multiple components.
    
6. Action Result filters: Action Result filters are used to modify the action result returned by a controller action method. They can be used to modify the result in the context of the HTTP request.
    

Overall, the use of filters in MVC allows developers to modularize and reuse common functionality across multiple components of an application, leading to cleaner, more maintainable code.