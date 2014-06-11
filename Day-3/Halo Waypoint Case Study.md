#Halo Waypoint Case Study

*Bing Huan Chio*

[cbingh@microsoft.com](cbingh@microsoft.com)

##Why Orchard?

  - (MS Game Studio) => .NET based
  - Web-based admin portal
  - Azure deployment setup
  - Well-maintained, well-supported, open-source code base
  - Free
  - **Extensibility**
  
> If we wanted to make changes [to the [microsoft.com](http://www.microsoft.com) CMS], we had to submit a feature request to that team.

##Orchard Customization

*v1 Release (March 2014)*

  - ADFS integration for security
  - TinyMCE editor updates: preview CSS inline
  - **REST API**: Halo Waypoint is not just a website.
  
> For us, Orchard was content storage. We need to get content out to a number of different platforms.

###REST API

```csharp
//specific by id
"/content/{id}"

//via autoroute path
"/content/{type}?vanitypath={path}"

//children (containables) of a content item
"/contents/{id}/children"

//all contents of a specific type
"/contents/{type}"

//get related content using taxonomy
"/contents/{id}/related"

//get all the taxonomy terms associated with contents of a given type
"/contents/{type}/taxonomy"
```

##Challeneges

  - Ramp up into customizing Orchard took longer than expected
  - Understanding how to optimize the queries: don't use `ContentManager` for everything

##Future

  - Bulk localization
  - Region content part: specify which region content is available in (not just language)
  - REST API improvements
    - Expanded for GEt
	- PUT
	- moving to Identity over ID (just a simple incremental index)
	- Content Picker by reference only
  - Various Admin UI updates
    - customize experience (for authors) using Content Picker field
	- Improve TinyMCE editor to support multiple config options
	- Name/Value pair field
  
