#Created by Hellocomputer - Built with Orchard

*Samuel Goldenbaum*

[Youtube video](https://www.youtube.com/watch?v=WTKZDOE7w7U)

Hellocomputer: digital arm of FCB (Foote, Cone & Belding) marketing agency.

Every day: **code review!**

##Case Study: Toyota

[Toyota South Africa](http://www.toyota.co.za)

Great example of Orchard as both a platform (e.g. bringing data into Orchard from external services) and CMS

  - Complete rebuild in 2013
  - Focus on conversions:
    - easy access to ranges and models
	- easy access to dealer info
	- reduce clicks
	- create WOW factor

  - Built on Orchard 1.7.x
  - Web API exposing JSON data
    - gzipped
	- using local storage (if available) to store large payload at initial request
	- filtering/computation/comparison done on client-side reduces stress on servers
  - Backbone.js for UI composition
  
##Case Study: JTB (Jamaica Tourism Board)

[Visit Jamaica](http://www.visitjamaica.com)

Great example of Orchard as a CMS for large, high-traffic website

  - complete rebuild, 3 month project in 2013
  - immersive experience

  - Built on Orchard 1.8x
  - Web API exposing JSON data
  - Backbone.js for UI composition
  
  - (3rd party) vendors list their properties and services (they don't login and manage content)
  - Trip planner -> add items from various Vendor pages to your itinerary
  - Interactive/dynamic map with layers for Vendor types
    - Custom Google maps base-layer styles

##Case Study: FCB

[FCB staging site](http://fcb.hellostaging.co.za)

Great example of a highly visual, creative/marketing site.

  - fully responsive using Bootstrap
  - AJAXify: background page loading, rendering images off-canvas, attaching/detatching scripts on page-by-page basis
    - will likely release as a module soon
  - IE9 limited to 4,000 CSS selectors! 
  
##Case Study: FCB Events iPad App

Front-end is native iOS app

Back-end is Orchard!

  - when attendees get to conference, access code connects app to back-end
  - Web API to serve content out as JSON
  - when internet connected, can check back-end for updates
  - manage attendees, agenda, points of interest, etc. inside Orchard
  
##With Great Power Comes Great Responsibility

  - don't overwidgetize! (DB calls don't necessarily scale as requests go up)
  - sanity check - use profilers: NHibernate Profiler (DB)
  - New Relic to monitor server health and application status
  - Blitz for load testing
