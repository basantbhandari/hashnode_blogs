---
title: "what is the template to create a web API in dotnet core"
datePublished: Fri Mar 03 2023 13:07:07 GMT+0000 (Coordinated Universal Time)
cuid: clesjvcv6000f09lbe62sae1f
slug: what-is-the-template-to-create-a-web-api-in-dotnet-core
tags: dotnet, web-api

---

To create a new Web API project in .NET Core, you can use the dotnet CLI and the "webapi" template. Here are the steps to create a new Web API project:

1. Open a command prompt or terminal window.
    
2. Navigate to the directory where you want to create the project.
    
3. Run the following command to create a new Web API project:
    
    ```csharp
    dotnet new webapi -n <project-name>
    ```
    
    Replace `<project-name>` with the name of your project.
    
4. Once the project has been created, navigate to the project directory:
    
    ```csharp
    cd <project-name>
    ```
    
5. You can now run the project using the following command:
    
    ```csharp
    dotnet run
    ```
    
    This will start the Web API project and it will be accessible at [`http://localhost:5000`](http://localhost:5000) in your web browser.
    

The "webapi" template creates a basic Web API project that includes a sample controller, model, and startup configuration. You can customize the project to suit your needs by adding additional controllers, models, and configuration settings. You can also use tools such as Visual Studio or Visual Studio Code to edit the project files and add additional functionality to your Web API.