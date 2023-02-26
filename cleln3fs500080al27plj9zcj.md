# Server.Transfer() vs Response.Redirect()

Server.Transfer() and Response.Redirect() are both methods in [ASP.NET](http://ASP.NET) used to transfer control from one page to another page. However, they differ in how they transfer control and what happens behind the scenes.

Server.Transfer():

* Server.Transfer() transfers control to another page on the server side without the client knowing about it.
    
* The client's URL remains the same as the original request, and the client is unaware that the page has changed.
    
* The transfer occurs entirely on the server, which means that the server-side page logic is preserved, and the control is transferred to the new page.
    
* Server.Transfer() is faster than Response.Redirect() because it does not require a round-trip to the client.
    

Response.Redirect():

* Response.Redirect() redirects the client to a new URL, typically on a different server or domain.
    
* The client's URL changes to the new URL, and the client is aware that a redirection has occurred.
    
* Response.Redirect() requires a round-trip to the client because the redirection headers must be sent to the client.
    
* Response.Redirect() can be used to redirect the client to an external URL or a different website.
    

In summary, Server.Transfer() is useful when you want to transfer control to another page on the same server without the client knowing about it, while Response.Redirect() is useful when you want to redirect the client to a new URL or a different website.