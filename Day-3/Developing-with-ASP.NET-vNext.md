#Developing with ASP.NET vNext

*Taylor Mullen*

[Youtube video](https://www.youtube.com/watch?v=kqgIByKn9Wk)

##Install VS14 CTP1

(This is not side-by-side safe)

[Visual Studio 14 CTP1](http://www.asp.net/vnext)

##New Empty vNext Project

Inside `Startup.cs`: order matters! (specifying "middlewares")

###Setting up configuration

```csharp
//create a config object for a config.json file
var config = new Configuration().AddJsonFile("config.json");

//use some values e.g. in { "jdata": { "jfoo": "From config.json" } }
var jdata = config.Get("jdata:jfoo");
```

###Setting up MVC

```csharp
//after adding dependency to project.json

//add the middleware for MVC
app.UseServices(services => services.AddMvc());

//use it!
app.UseMvc();
```

###ViewComponents

> A modular way to execute something "sub-action" like.

> Razor can now execute async

###Running from the CLI

No need for IIS

  1. Add the dependency for Microsoft.AspNet.Server.WebListener to `project.json`
  2. Add the command "web" to `project.json`
  
Then...

```
cd "path/to/web/app"

//start the self-hosted server
k web
```

Using different runtimes

```
//get a list of available runtimes
kvm list

//set one as the current
kvm use 0.1-alpha-0506

//restart (self-hosted) server
k web
```

> When you publish your app, you publish the runtime with it. You deploy and use **exactly** what you were developing on. 
