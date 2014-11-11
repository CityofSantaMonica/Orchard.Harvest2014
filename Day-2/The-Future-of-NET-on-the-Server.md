#The Future of .NET on the Server

*Elon Lipton*

*Scott Hunter*

[Youtube video](https://www.youtube.com/watch?v=DYph_MtQLJw)

**.NET Stats**

1.8B active installs of .NET

6M active .NET developers

**What are we hearing from our customers?**

> 1. Our role is more important than ever before
> 2. We are required to innovate and deliver much faster
> 3. I need a cross-device development strategy
> 4. Open Source enriches the platform and the community
> 5. ...but I have existing applications to run and evolve

##New Approach to building .NET

  - .NET Innovation
  - Flexibility and agile delivery: continuous/modular delivery
  - Openness: transparent, open, community-driven
  
##ASP.NET vNext and the Modern Web

  - Totally modular
  - Seamless transition from on-prem to the cloud
  - Open Source w/Contributions
  - Faster Development cycle
  - Choose your editors and tools: e.g. edit in the cloud, build in the cloud
  - Cross platform: Mac, Linux support
  
###Modern Web - Agility

  - Faster Development cycle
    - features are shipped as packages
	- **framework ships as part of the application**	
  - More Control
    - Zero day security bugs patched by MS
	- Same code runs in dev and prod
	- Developer opts into new versions, allowing breaking changes
	
> Packages are now first-class citizens in VS

> One of the goals...less "magic" than before

###Modern Web - Fast

  - Runtime Performance
    - Faster startup time
	- Lower memory / higher density (> 90% reduction)
	- Modular, opt into just features needed (session state, cache, etc.)
	- Use a raw socket, framework, or both
  - Development productivity and low friction
    - Edit code and refresh browser
	- Flexibility of dynamic environment w/the power of .NET
	- Develop w/VS, 3rd party, cloud
	
###Modern Web - Cloud

  - Cloud ready
    - configuration: get rid of web.config transforms!
	- session
	- cache
  - Diagnostics
    - Run/Debug in cloud
	- Tracing/logging w/o redeploy
	
> We would love to have Orchard as SAAS inside Azure, 1-click setup of complete CMS solution	
	
###Modern Web - Cross Platform & Open

> We're thinking about getting full IntelliSense in Sublime Text

> As far as [we're] concerned, and [our] legal team is concerned, you can do whatever you want with those [MS package] binaries.

> We're using Orchard...to help drive the new direction of EF, MVC, etc.

##ASP.NET vNext Compatibility

  - Web Forms, MVC5, Web API 2, Web Pages 3, SignalR 2, EF6 => fully supported  
  - MVC, Web API, Web Pages 6, SignalR 3, EF7 breaking chages:
    - new project system
	- new configuration system (JSON based)
	- MVC/Web API/Web Pages *will merge*
	
##New ASP.NET vNext Web Application Project

  - No edit/rebuild -> edit and reload browser (compilation in background)
  - References: displayed as tree structure to show hierarchy
  - project.json (replaces the .csproj file) **the source of truth**
    - similar to Orchard Module.txt: the system sees this file, knows that folder contains a project, filewatcher
    - full Intellisense inside JSON file!
	- automatic NuGet package restore by changing project file
	- register custom CLI commands/parameters
  - Startup.cs replaces Global.asax
	- customized config locations
	- Middleware composition to build a request pipeline for e.g. serving static files, cookie-based auth, defining routes
  - Dependency Injection built in to the system, can wire-up any existing .NET DI frameworks
    1. create interface, implement as class
	2. register interface in Startup.cs (3 scopes to choose from by default)
  - Don't even have to run in IIS (e.g. for testing) -> commmand line "K" launcher
  
