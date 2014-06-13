#The Future of Orchard

*Sebastien Ros*

##Web Evolution

  - Static pages: manage HTML pages, reuse Notepad
  - Dynamic pages: manage databases, reuse APIs
  - CMS: manage content, reuse modules/themes
  - SAAS: manage software, reuse ?
  
##Open-*

  - Source code
  - Steering Committee: 5 members, elected by community
  - Weekly meetings: walk-ins welcome, on YouTube
  - Discussions forums: open design discussions
  - Documentation: GitHub
  
##Advantages

> What do we do well in Orchard?

  - Content Types
  - Media
  - Projections
  - Workflows
  - Extensibility
  - ASP.NET MVC
 
> What do others do better?

  - DotNetNuke: marketing, widget system, "they are not French"
  - Drupal: community, company behind them
  - SiteCore: support, resources (books), localization
  - Sitefinity: user-friendly (drag/drop)
  - Umbraco: training, content organization (in a tree)
  - WordPress: themes, easier to approach for "normal" users, setup
  
##Orchard vNext

> **Brochard**: the CMS you can tell your bro to use

New major version implies *breaking changes* (no guided migration path). But it doesn't break *everything*:

  - Modularity
  - Dashboard
  - Content types, Content Parts
  - Versioning
  - Multi-tenancy
  - Event bus
  - Existing modules
  
##What do we need to change?

###Developer's Perspective

  - Data access?
  - Use Nuget more?
  - Simplify module development? Shapes, abstractions, placement

###User's Perspective

  - Performance? No, it's fine
  - New back-end/Admin?
  
###Management Perspective
 
  - Remove bottlenecks: Sebastien (e.g. pull requests), triage
  - Move to GitHub?
  
##Data Access

> I'd like to simplify the story.

  - Useless abstraction
  - Content Query
  - Repository<>
  - Hql
 
Remove limitations, improve performance.

###Constraints

Relational vs. Document: we need **both**

> We can't fight with SQL

  - choice (SQL CE, MySQL, SQL Server, etc.)
  - wide-spread developer knowledge
  - existing, well-known tooling
  
> Orchard needs documents though, types and parts are documents!

##Theming

> Theming should not be an obstacle to creativity. 

This is **not about** "How do I change the title red?"

###Two Sides

  - Custom themes
  - Reusable themes
  
##Caching

  - Output Cache is limited in reverse proxy invalidation
  - Business cache: simple implementation (get/set)  
  - Settings cache: doesn't work in a farm
  
##Commands

  - Use PowerShell?
  - Online commands execution?
  
##Content Management

  - Drivers? Keep/remove/change?
  - Handlers? Keep/remove/change?
  - Migrations are good.
  
##Environment

  - Autofac
  - Configuration: shell settings
  - Processing engine
  - Indexing: is Lucene ok?
 
##ASP.NET vNext

> Does ASP.NET vNext have a place for Orchard?

> Yeah, we need Orchard to work there. It's important for [the ASP.NET team], because it validates whether or not ASP.NET vNext works.

###Benefits

  - Roslyn compiler: add new features to the language, type interception
  - Pay for play
  - Performance
  - Portability
  
###Risks

  - New platform => unknown bugs
  - CLR vs. Cloud CLR: where do we go first?  
