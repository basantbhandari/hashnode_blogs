# difference between ViewData, viewBag, tempData

In [ASP.NET](http://ASP.NET) MVC, ViewData, ViewBag, and TempData are all mechanisms for passing data between the controller and the view. However, they differ in their scope, lifespan, and behavior. Here's a brief summary of the differences:

1. ViewData: ViewData is a dictionary object that is available within the controller and the view. It is used to pass data from the controller to the view. ViewData has a short lifespan and is only available for the current request. If you want to pass data between different requests, you will need to use another mechanism.
    
2. ViewBag: ViewBag is a dynamic object that is available within the controller and the view. Like ViewData, it is used to pass data from the controller to the view. However, ViewBag has a slightly longer lifespan than ViewData and is available until the end of the current request. ViewBag is useful for passing small amounts of data between the controller and the view, but it can be slower than other mechanisms due to its use of dynamic binding.
    
3. TempData: TempData is a dictionary object that is available within the controller and the view. It is used to pass data between different requests. TempData has a longer lifespan than ViewData and ViewBag and is available for the current request and the next request. This makes it useful for passing data between different actions or controllers. However, TempData should be used with caution, as it can lead to unexpected behavior if not used correctly.
    

In summary, ViewData and ViewBag are used to pass data from the controller to the view within the same request, while TempData is used to pass data between different requests. ViewData and ViewBag have a short lifespan, while TempData has a longer lifespan but should be used with caution.