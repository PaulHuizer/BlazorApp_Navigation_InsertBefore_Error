# BugReport - Issue Reproduction  
On Blazor WebAssembly DotNet 10 (dotnet --version 10.0.100)

**Description:**  
Navigating from InteractiveWasm route to a Static/InteractiveWasm route fails.  

In the repro app, clicking Counter and then Home → navigation error.  
In the Chrome console, an error appears: "InsertBefore issue" in blazor.web.js  

**Regression:**  
This works fine in DotNet 9.0; the error appears in DotNet 10.0.  

**Reproduction:**  
For easy reproduction, this repo has two identical projects: one for .NET 9.0 and one for .NET 10.0.  

To reproduce the OK and the NOK version:  
- Load the .NET 9.0 version in VS2022 and run it. Follow the steps on the home page → **OK**.  
- Load the .NET 10.0 version in VS2026 and run it. Follow the steps on the home page → **NOK**.  

![InsertBefore error screenshot](https://github.com/PaulHuizer/BlazorApp_Navigation_InsertBefore_Error/blob/main/BlazorApp10/imgs/insertbeforeerror.png?raw=true)

*Workaround I*
 A temporary workaround is to force a full reload via NavigationManager.NavigateTo(url, forceLoad: true).

*Workaround II*
Another workaround is downgrading back to .NET 9, but ideally we would continue on .NET 10.


**Update I**
Based on identical error, this bugreport is added to the following issue:
[.NET 10 Blazor navigation from wasm to interactive server broken (#64472)](https://github.com/dotnet/aspnetcore/issues/64472)

**Update II**
After further efforts to find the difference between working and problematic pages, I found the following:
If a page does not have a PageTitle tag, it shows in the browsertab localhost:xxx/somename, from that moment on the nav is broken.

*Workaround III*
Add a PageTitle tag: <PageTitle>SomePageName</PageTitle>

I tried and checked the bugreport.zip from the first gibhub issue, but that appears to be a different issue.
A new github issue is created here: [aspnetcore issue #64522](https://github.com/dotnet/aspnetcore/issues/64522)

