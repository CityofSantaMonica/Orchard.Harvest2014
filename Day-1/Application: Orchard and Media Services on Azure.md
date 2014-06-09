#Application: Orchard and Media Services on Azure

*Ross Gardler - President of Apache Software Foundation*

> [Open Source] is not just about use, it's about giving back...

*Roopali Kaujalgi*

Microsoft Open Technologies, wholly owned subsidiary of Microsoft. Focused on open source, open standards and interoperability.

[Dash-JS](https://github.com/Dash-Industry-Forum/dash.js): a reference client implementation for the playback of MPEG DASH via Javascript and compliant browsers.

##MS Open Tech

  - internal ask for Azure Media Services solution
  - open source prototype
  - added as Orchard module, maintained by community and MS Open Tech

##Azure Media Services

  - complete cloud hosted media solution
	- ingestion
	- encoding
	- format conversion
	- content protection
	- on-demand streaming
	- live streaming (preview mode right now)

Many customers on Azure Media Services today: NBC Sports, The CW, XBOX...

##Azure Media Services in Orchard

  - connect to Azure Media Services account
  - upload content via Orchard dashboard
  - select encoding presets, add metadata, define allowed extensions, etc.
  - upload video, thumbnail file, translation caption files, etc.
  - create/queue "cloud job" e.g. encoding after upload
  
##Features planned for version 2

  - subscribe to Azure Media Services from within Orchard
  - bulk ingest or ingest from FTP, etc.
  - importing one or more existing assets from Azure Media Services
  - Task chaining
  - generation of thumbnails
  - custom presets
  - end to end encryption
