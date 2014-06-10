#AngularJS and ASP.NET

*Damian Edwards*

> Moving foward, you'll see...more focus on the client [from the ASP.NET team]

##ASP.NET Single Page Application Future

  - *blessed stack*: group of tech ASP.NET is "bettting on" for front-end
  - **AngularJS**
  - jQuery
  - Boostrap
  - LESS/SASS
  - TypeScript (optional)
  - Grunt: task runner (kind of like MSBuild, but not really)
  - Bower: client-side package manager (like NuGet for the browser)
  
##AngularJS Introduction

  - Controllers: more like a ViewModel (i.e `knockout.js`)
  - Views: where you compose the UI
  - Services: reuse across controllers, business logic, etc.
  - Directives: extend HTML syntax, interact w/DOM (will be replaced by Web Components)
  - Filters: simple functions for pre-processing before databind
  
##Music Store SPA

[MusicStoreSPA on GitHub](https://github.com/aspnet/MusicStore/tree/master/src/MvcMusicStore.Spa)

> Break people out of the idea that the client-side part of the application is "small"...

> [/Client/ng-apps/] are islands of SPA functionality

> Use *functional areas* for the organization of your source code

An underpinning of AngularJS is **dependency injection**, one of the core facets of how it works.

###Server-side Rendering

> When I go the SPA approach, is the server only for rendering JSON?
> What can we do to enhance the application as a whole by leveraging Server-side rendering?

**Razor Helpers!**

Using server-side rendering to create the template that AngularJS can use to render the data.

> Looking to fix the problem of composing HTML elements/attributes in Razor

##Future

  - Bower VS support
  - NPM VS support
  - Grunt VS support (running, scraping output, debugging)
  - Scaffolding of service proxies from server-side APIs
  - Full IntelliSense for AngularJS in views (HTML) & JS/TS
  - Templates & snippets
