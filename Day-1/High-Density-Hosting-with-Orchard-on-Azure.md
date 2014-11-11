#High Density Hosting with Orchard on Azure

*Sebastien Ros*

[Youtube video](https://www.youtube.com/watch?v=0WK1ovH_lb0)

##Project

Migrate [weblogs.asp.net](http://weblogs.asp.net) (~750 individual blogs) to Orchard

###Requirements

  - Hundreds of blogs
  - Hosted on Azure
  - ASP.NET
  - Cut costs of prev platform
  - Improve w/features and themability for users
  
##Infrastructure

A **node** scales horizontally (4 of these on a single Azure instance)

  - Azure Web Site (not VM)
  - Azure SQL Database (not VM)
  - Azure Cache
  
##Content Migration

  - Neudesic export BlogML
  - Convert to (Orchard) Recipe
    - posts
	- comments
	- users (new passwords)
	- based on a template recipe
  - Generate a commands file (automating recipe processing)
  - Dedicated VM (on East Coast, where Azure nodes are hosted, for improved speed)

##Modules

  - NGM.OpenAuthentication
  - Webadvance (sitemap)
  - Custom
	- List existing tenants
	- Blog post notification
	  - Azure queue
    - Theme (TheBoostrapMachine)

##Performance

  - Bottlenecks
    - Memory
	- DB queries
	- CPU
  - Testing
    - Load testing (how many blogs can we host, how many users can hit them)
		- ApacheBench command line tool
	- End to end (a particular blog's performance)
  - Problems for 1 site not the same as for 750 sites
  
###Memory

  - Memory consumption: first site 150MB, each tenant 10MB
  - 7GB -> 700 tenants in 32 bits
  - Memory limit of IIS process in 32 bits: 2GB
  - -> 200 tenants per IIS process
  - -> 4 websites sites per machine
  - Cache is externalized (in Azure): don't have to pay for RAM for output cache
  
###Database
  
  - Background tasks in Orchard (every minute by default)
    - Alias updater: checks DB to sync Content Slugs
	- Scheduled Tasks
	- Workflow timer
	- Search engine
  - 4 queries/minute -> 750 * 4 = 3000 queries/min -> 50 queries/sec
  - DISABLE useless background tasks!
  - DB granularity
    - one DB per node w/table prefixes (3MB memory footprint per tenant)

##Operations

  - Deployment
    - Webdeploy (first time)
	- FTP
	- SCM: Azure websites tool
	  - logs
	  - CMD/Powershell
	  - Extensions
	  - in-place editing
  - SQL manager
	- batch SQL queries e.g.
	```SQL

	SELECT 'UPDATE ' + table_name FROM sys.tables WHERE table_name LIKE '%_Settings'
```
  
##Cost

  - 1 Large Azure Websites basic instance: $223
  - 4 SQL Azure DB: $40 total
  - 4 Azure Cache Services: $50 total
  - Blog stroage: < $2
  - Network: N/A
  
##Impact on Orchard Project

  - Performance
    - MVC routes (to handle ~50,000 routes)
  - Bug fixes
	- Sessions disposal
  - Improvements
    - Multi-tenancy
	- Tag Cloud
	- Archives page
	- Comments notification
	- Closed comments
	- Output cache

##Conclusion	
	
  - *Yes, Orchard can be fast and easy to use*
  - *Multi-tenancy enables new hosting scenarios*
  - *Azure well supported by Orchard*
