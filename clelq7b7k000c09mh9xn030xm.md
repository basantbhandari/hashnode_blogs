# response code in web API?

In Web API, response codes are used to indicate the status of the HTTP response returned by the server. The HTTP response status codes are standardized codes that are used by servers to communicate with clients, indicating the outcome of a particular request.

Some of the common HTTP response status codes used in Web API include:

* 200 OK: This status code indicates that the request was successful and the server has returned the requested data.
    
* 201 Created: This status code indicates that a new resource has been successfully created on the server.
    
* 204 No Content: This status code indicates that the request was successful but there is no content to return.
    
* 400 Bad Request: This status code indicates that the client's request was invalid or malformed.
    
* 401 Unauthorized: This status code indicates that the client is not authorized to access the requested resource.
    
* 404 Not Found: This status code indicates that the requested resource was not found on the server.
    
* 500 Internal Server Error: This status code indicates that there was an error on the server that prevented it from fulfilling the request.
    

These status codes are important in Web API because they allow the client to determine the outcome of their request and take appropriate action. By returning a specific status code, the server can indicate whether the request was successful, whether additional action is required by the client, or whether an error occurred.