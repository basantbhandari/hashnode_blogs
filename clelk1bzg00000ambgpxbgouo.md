# What are the different Authentication in dot.net MVC

There are several different types of authentication that can be used in an [ASP.NET](http://ASP.NET) MVC application. Here are some of the most common authentication types:

1. Forms authentication: Forms authentication is a widely used authentication method in [ASP.NET](http://ASP.NET) MVC. It involves storing user credentials in a database or other user store and using cookies or tokens to authenticate users as they move between pages in the application.
    
2. Windows authentication: Windows authentication is a method of authentication that uses the Windows operating system's security features to authenticate users. It is typically used in intranet environments where users are already logged in to a Windows domain.
    
3. Token-based authentication: Token-based authentication involves using a token or security token to authenticate users. This method is commonly used in web APIs and Single Page Applications (SPAs), where the server provides a token to the client that is used for subsequent requests.
    
4. OAuth authentication: OAuth is an open standard for authorization that is commonly used to allow third-party applications to access user data without requiring the user to share their credentials. OAuth can be used for authentication as well as authorization.
    
5. OpenID Connect authentication: OpenID Connect is an authentication protocol that is built on top of OAuth 2.0. It provides a standardized way for applications to authenticate users using an identity provider such as Google or Facebook.
    
6. Two-factor authentication: Two-factor authentication involves requiring users to provide two different types of authentication, such as a password and a verification code sent to their mobile phone, in order to access the application.
    

Overall, the choice of authentication method will depend on the needs of the application and the level of security required. [ASP.NET](http://ASP.NET) MVC provides built-in support for several different authentication methods, and developers can also implement custom authentication methods if needed.