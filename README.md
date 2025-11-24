# BugReport - Issue Reproduction  
On Blazor WebAssembly DotNet 10

**Description:**  
Navigating from InteractiveWebAssembly route to InteractiveServer route fails.  

Clicking Counter and then Home → navigation error.  
In the Chrome console, an error appears: "InsertBefore issue" in blazor.web.js  

**Regression:**  
This works fine in DotNet 9.0; the error appears in DotNet 10.0.  

**Reproduction:**  
For easy reproduction, this repo has two identical projects: one for .NET 9.0 and one for .NET 10.0.  

To reproduce the OK and the NOK version:  
- Load the .NET 9.0 version in VS2022 and run it. Follow the steps on the home page → **OK**.  
- Load the .NET 10.0 version in VS2026 and run it. Follow the steps on the home page → **NOK**.  

![InsertBefore error screenshot](https://github.com/PaulHuizer/BlazorApp_Navigation_InsertBefore_Error/blob/main/BlazorApp10/imgs/insertbeforeerror.png?raw=true)

[.NET 10 Blazor navigation from wasm to interactive server broken (#64472)](https://github.com/dotnet/aspnetcore/issues/64472)
