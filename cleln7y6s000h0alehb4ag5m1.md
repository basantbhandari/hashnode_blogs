# Where ViewState is stored after the page postback?

After a page postback, the ViewState is stored in a hidden field in the page's HTML. This hidden field is sent to the client browser as part of the response, and the browser sends the value of the hidden field back to the server with subsequent requests.

The hidden field is typically named "\_\_VIEWSTATE" and its value is encrypted and encoded to prevent tampering by the client. The ViewState data includes the current state of the page and its controls, such as values entered into textboxes, selected items in dropdown lists, and the visibility and enabled state of controls.

When the page is posted back to the server, the ViewState is decrypted and used to restore the state of the page and its controls. This allows the server-side code to retrieve the values entered by the user and continue processing the request as if it was never interrupted.

It's important to note that ViewState can increase the size of a page, which can impact performance and load times. Therefore, it's recommended to only use ViewState when necessary and to consider other alternatives, such as session state or cookies, for storing data that needs to persist across postbacks.