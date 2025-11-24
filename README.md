**Description:**
Navigating from InteractiveWebAssmbly route to InteractiveServer route fails.

Clicking Counter and then Home ... navigation error. 
In the Chrome console, an error appears: "InsertBefore issue" in blazor.web.js

This works in DotNet9.0, and the error appears in DotNet10.
This repo has 2 identical projects, one for dotnet 9.0 and one for dotnet 10.0


**Reproduce**
So, to reproduce the OK version:
Load the Dotnet 9.0 version of the app in vs2022 and run it. Follow the steps on the home page.
Load the Dotnet 10.0 version of the app in vs2026 and run it. Follow the steps on the home page.

On dotnet 9.0 it seems to work fine. On Dotnet 10, the navigation fails.

