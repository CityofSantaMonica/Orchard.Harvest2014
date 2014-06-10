#AMC Theaters Case Study

*Travis Maddox*

*Adam Anderson*

Bulk of their content [e.g. on homepage] is surfaced through API layer, called from Orchard widgets.

Custom admin area "Theater Media" to manage images/media metadata for each Theater. Created before new *Media Manager* module.

POS at Theaters sends seating information up to Orchard site, to render seating charts. 

##Inception

> AMC used to...outsource marketing, website, etc. until we had bad experiences with other CMS companies [*it was **Ektron***], couldn't handle e.g. more than 50 concurrent users.

> The *developers* chose the CMS, for the first time!

##High-Level overview

> If you don't currently use New Relic, it's worth it.

Self hosted, 8 servers (scale up to 20 if needed), 4 cores each, solid state, 8GB RAM

4 developers on a daily basis in Orchard. Team of data architects. Team of API devs. 

Release every Wednesday. Every code check-in goes through CI. Automated load and regression testing every week. 

30Mil pageviews over 30 days.

Growth since Orchard: 30-40% growth every year -> constantly refactoring, looking at performance.

Orchard 1.6: 20ms database response time, Orchard 1.8: 5ms database response time.

##v2.0 Challenge: Web Service Data

  1. Custom Route & Constraint
  2. Custom Controller
  3. Get Data via Service over HTTP
  4. Populate new (Orchard) content item with Data
  5. Let Orchard handle compositions
  
##v2.0 Challenge: Performance

  1. Server performance: the amount of time it took to render a page  
    - Turn on Contrib.OutputCache module => no user specific HTML  
	
  2. Mobile device bandwidth: rich desktop app to resource constrained devices
    - mobile specific theme using user-agent sniffer
  
  3. Individual HTTP requests from browser
    - custom resource bundler
	- multi-environment, multi-server
	- SQL Server as distributed cache
	
##v3.0

  - fully responsive
  - Media Management
    - modified Media module to use CDN
	- added Image Optimization
	
##v4.0

  - AMC Stubs (loyalty program) integration
  - Public Authentication
    - When you are logged in to the website -> no Output Cache!
	
##v4.0 Challenge: Performance

  1. For authenticated users
  2. For mobile users
  3. Perceived performance
 
> Solution: *don't* do everything we did before. 
 
> The metric we decided to go with to address these issues, was users' perceived performance. "How fast can I interact with the thing that I want to".

  - Re-render portion of output cache (substitution cache)  
  - Inline user-specific JSON to avoid callback
  
