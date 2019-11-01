# WebOptimizerHangsDemo
Using WebOptimizer, if you have a stylesheet with a protocol less URL for a background image (e.g. url(//www.somesite.com/image.jpg) 
and try to render that stylesheet using the WebOptimizer inline attribute, it causes the entire application to hang at startup.
It just spins endlessly and eventually times out without an error message ever getting displayed.

### Steps to Reproduce:

1. Create a new ASP.NET Core Web Application
2. Add WebOptimizer package
3. Add WebOptimizer to Startup.cs
4. Add WebOptimizer Tag Helper to View Imports
5. In site.css, add a background image property with a protocol relative url (e.g. url(//www.somesite.com/image.jpg )
6. Add the "inline" attribute to the link tag for the stylesheet in _Layout.cshtml
7. Start the application and notice it hangs

This is happening whether the applications is ran via IIS Express or as a standalone process using dotnet run.

NOTE: Once you remove the protocol relative URL or change it to use a specific protocol the app will start normally.
