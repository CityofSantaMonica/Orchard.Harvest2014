#Orchard - What's Next?

*Sebastein Ros*

##Audit Trail

A security-related chronological record of "what happened"

###Use Cases

  - Be able to see the full history of a content item:
    - who modified, what, when
	- history link inside Summary Admin for content item
  - Be able to see the activity of the website (module/feature interactions, settings changed, etc.)
    - filter by user
	- filter by date
	- filter by category/event (user logged in/out, feature enabled/disabled, etc.)
  - Display the version at the time of the record
    - view the diff
	- Restore
  - Archive the audit trail
  
###Security

  - Audit trail record cannot be deleted!
  - Permissions: viewing, changing settings
  
###Implementation

  - AuditTrailPart
  - AuitTrailEvenProvider: provide new kinds of events to be added to Audit Trail in custom modules
  - AuditTrailRecord: storing could be make extensible so that other RMS could store it
  
**Very soon, this will be a part of the Orchard core**
  
##Deployment

Goal: publish a website from e.g. a dev box to a production box
  
###Deployment Plans

*What to push*

  - Made of content sources
  - Bundles: select specific content items
  - Query: filter content items based on a query (e.g. all content updated in last week)
  - Assets: files that should be deployed (css, views, media, etc.)
  - Metadata
  - Content Diff

e.g. "every Sunday, we push the News items"

###Deployment Channels

*How to push*

  - Web API
  - FTP
  - Git
  - **Extensible**
  
###Deployment Processors

*filters to enhance deployment package*

##REST API

###Reusable Features

  - Authentication/Security
  - Serialization
  - Materialization - something to alter the data before it is presented to the request
  - Pagination
  
###Content Manager

    /documents/id1,id2,id3
	
	/documents/type/Production/page/1?take=10
	
`PUT` using the Import feature

###Lucene

    /api/search?q="type='Product'"
	
##Dynamic Layout

Existing modules
  - Onestop
  - IDeliverable

What is missing?
  - Container's lifetime. Content is published/drafted/removed based on its container
  - Drag and drop layouts: rows, columns, containers, content (like Workflow)
  - Inline editing *in the admin*
  
##Admin Theme

  - Want a customizable dashboard - widgets, reports, etc.
  - Search bar
  - Content organization: folders, taxonomy, etc
  
##Ecosystem

  > We need a new website!
  
###Gallery Improvements  
  
  - Need an extension harvester to pull from e.g. Git, Dropbox
  - Webhooks to Github
  - Polling
  
"Works on my machine" - indicate what version modules are working on, how many users have successfully got it working, etc.

##Documentation

> It's a blank slate!

> Needs to be community-driven
