# how validations work in MVC dotnet

In [ASP.NET](http://ASP.NET) MVC, validation can be performed on user input data using model validation or custom validation.

Model validation is a built-in feature in [ASP.NET](http://ASP.NET) MVC that automatically validates user input data against the rules defined in the model class. Model validation rules can be defined using data annotations, which are attributes that you can apply to properties of the model class. Examples of data annotations include "Required", "StringLength", "Range", and "RegularExpression". When the user submits a form, the input data is automatically validated against these rules, and any errors are added to the ModelState object.

Custom validation, on the other hand, allows you to define your own validation rules and logic. This is useful when you need to perform more complex validation that cannot be easily defined using data annotations. To perform custom validation, you can create a custom validation attribute class that inherits from the ValidationAttribute class, and then apply this attribute to the property of the model class that requires validation. The custom validation logic is then executed when the user submits the form, and any errors are added to the ModelState object.

Once validation is performed, you can display error messages to the user by checking the ModelState object in the controller action method, and returning the view with the errors if necessary. To display the error messages in the view, you can use Html.ValidationMessageFor helper method, which generates HTML markup for the error messages based on the validation rules defined in the model class.

In summary, [ASP.NET](http://ASP.NET) MVC provides built-in model validation using data annotations, as well as custom validation using custom validation attribute classes. Validation errors are added to the ModelState object and can be displayed in the view using the Html.ValidationMessageFor helper method.