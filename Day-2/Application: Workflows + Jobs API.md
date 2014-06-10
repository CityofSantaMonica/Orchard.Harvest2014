#Application: Workflows + Jobs API

*Sipke Schoorstra*

> Workflows allow a highly-configurable program with logic/parameters that isn't hard-coded in code.

##What are Workflows?

A series of distinct programming steps, where each step is modelled as an activity.

###Demo: Content Approval

  - page is created, site admin is notified to approve or reject
  - page is rejected => contributor is notified via email, opportunity to make changes
  - loop until accept
  
In a DecisionActivity:  
  
    Workflow.SetState("SomeKey", "SomeValue");
	
	Workflow.GetState("SomeKey");
	
In a SendEmailActivity:
    
	//use .Absolute to get a URL that works for the recipient
	{Contenet.EditUrl.Absolute}
	
Can add approve/reject button directly to the content editor surface
