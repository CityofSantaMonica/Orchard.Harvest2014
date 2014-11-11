#Building an Orchard SaaS - DotNest

*Lombiq Technologies: Zoltán Lehóczky, Benedek Farkas*

[Orchard Spring Harvest Challenge Youtube video](https://www.youtube.com/watch?v=zUOtuzvo7Hk)

[Building an Orchard SaaS Youtube video](http://youtu.be/zUOtuzvo7Hk?t=18m54s)

##What should SaaS do?

> We think it should work, it should work reliably, it should work fast, it should work "well", and it should work seamlessly.

###It should work reliably

  - stateless web servers and enhanced multi-node support for scaling out
  - feature guard: a service for restricting Orchard feature enable/disable
  
###It should work fast

  - tenant idle shutdown and runtime/storage quota management
  - Combinator enabled/configured, cookie-less static domain (YSlow: 98/100)
  - Caching reverse proxy (Application Request Routing [ARR]) with Orchard.OutputCache integration

###It should work well

  - MediaTheme
  - Liquid templating (created by Shopify, with "safety" in mind)
  
###It should work seamlessly

  - Automatic maintenances (e.g. for all tenants)
  - No-downtime deployments
  
##Deployemt

Goals: high abstraction, low interaction, zero downtime

###Historical Overview

1.
  - One repository to rule them all
  - Single tenant setup (OrchardHUN)
  - SQL CE database in the repository  
  - **Deployment from FTP or VS Web Deploy** 
  
2.
  - first deploy to a VM
  - multi-tenancy 
  - sub-repos for themes/modules
  - batch scripts calling `Orchard.exe` for switching environments (dev vs. prod)
    - shape tracing
	- YSlow
  - Databases migrated to SQL Azure
  - DB backups as SQL scripts in the main repository
  
3.
  - New tenant: Orchard Dojo
  - Azure VM
  - First generation PowerShell script to automate deployment processes
    - Staged publishing (2 applications, each swapping between staging and prod)
	- DB and media backup and replacement
	
4.
  - New tenant: Lombiq
  - Search for a CI/CD system: TeamCity
  - Second generation PowerShell scripts, PS remoting
  - Separate DB for staging and prod environments
  - Move to Azure Web Sites
  
5.
  - staged publishing to AWS
  - a few new features to TeamCity
  - better, smarter PowerShell scripts
  - Deployment events with Recipe Remote Executor (composite recipes): send Recipes to an API endpoint, execute per tenant
  
##The Toolkit

  - Microsoft Azure: VMs and Web Sites, Azure SQL and Blob Storage
  - TeamCity for CI/CD
  - PowerShell, MSBuild, NUnit
  - Lombiq Hosting Suite (Maintenance) and/or Recipe Remote Executor
  
###Pull and Build

  - Build VS solution
  - Run NUnit tests
  - Build parameters (for all projects) example: Remote debugging
    - Run a custom build in TeamCity that sets the build target to Debug
	- Deploy
	- Enable remote debugging for the website in Azure
	
###Swappping Website Slots

  - Updating AppSettings and ConnectionStrings (staging to production)
  - Backwards compatible DB changes
  - Disaster plan: swap again

###Backup

  - Daily, automatic backup of the production database
  - .bacpac format
  - Pushed into a repository

> Developed before Azure backup was available. It works, so we still use it.

##Orchard PaaS

  - **Orchard Developers!**
  - An all-in-one solution that makes Orchard developers' lives easier
    - portable package for the complete setup process
	- integrate to Microsoft Azure (maybe add-on?)
	- inlcude all the advantages by the Lombiq Hosting Suite
	- all this in a self-sevice manner
