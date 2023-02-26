# what are the events in the page life cycle? in which event is the control fully loaded?

Page life cycle events in [ASP.NET](http://ASP.NET) Web Forms:

1. Page Initialization: This event is raised when the page is initialized, and it is the first event in the page life cycle.
    
2. ViewState Loading: The ViewState is restored during this event.
    
3. Load Event: During the Load event, the page and its controls are fully loaded.
    
4. PostBack Event Handling: This event is used to handle any postback events, such as button clicks, that occur during the page's life cycle.
    
5. PreRender Event: This event is raised just before the page is rendered. This is typically where you would perform any last-minute changes to the page before it is sent to the client.
    
6. SaveStateComplete Event: This event is raised after the view state has been saved for the page and all controls.
    
7. Render Event: The Render event is the final event in the page life cycle. This event is used to render the page and all its controls to HTML.
    

The control is fully loaded during the Load event, which occurs after the ViewState is loaded. At this point, the control's properties have been initialized with the values from the ViewState, and any events associated with the control have been raised.