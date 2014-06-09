#Proligence, Projects, and Open Source

*Piotr Szmyd*

[Proligence website](http://www.proligence.pl)

[info@proligence.pl](info@proligence.pl)

[piotr.szmyd@proligence.pl](piotr.szmyd@proligence.pl)

##Orchard Testing Library

**[Orchard Testing Library on BitBucket](https://bitbucket.org/proligence/proligence.orchard.testing)**

  - makes unit testing Orchard components and shapes easier
  - mocks, helpers, base fixture classes for testing
    - drivers
	- handlers
	- content part
	- core services
	- etc.
  - based on NUnit and Moq
  
###Examples

1. Testing driver/auth

```csharp
[Test]
public void DisplayShouldNotCreateShapeWhenUserNotAuthorized()
{
    _orchardServices.AuthorizerMock.DenyWithoutMessage(SomePermission, _part);
    var result = (CombinedResult)_driver.InvokeDisplay(_part, String.Empty, ShapeFactory);
	
    Assert.That(result.BuildShapeMock("SomeDisplayShape"), Is.Null);
    _orchardServices.AuthorizerMock.VerifyAll();
}
```

2. Testing content handlers


```csharp
[Test]
public void ActivatingShouldNotWeldIdentityPartIfNotDirectoryContentType()
{
    ...		
}
```


3. Using content manager mocks

```csharp
[Test]
public void GetOrCreateDirectoryShouldCreateDirectoryWhenDirectoryDoesNotExist()
{
    _contentManager = new ContentManagerMock(MockBehavior.Strict);
    ...	
}
```

##Astoria Framework

**[Astoria framework on BitBucket](https://bitbucket.org/proligence/astoria)**

**[Asotria Orchard module on BitBucket](https://bitbucket.org/proligence/proligence.astoria.orchard-git)**

Quick and painless implementations of high performance back end services and APIs.

Requirement: move pieces of functionality from Orchard module to external process/machine with as little overhead as possible
  - some complex tasks/computation cannot happen inside Orchard due to performance considerations
  - need a way to pass data back and forth -> Orchard module

*Asotria aims to be for WCF what Orchard is for ASP.NET*

###Main Features

  - multiple hosting options (Windows Services and process host)
  - multiple transport methods (WCF only for now)
  - self-checkup and monitoring
    - watch dog mechanisms
	- performance counters
	- configurable logging
  - easy integration w/Orchard using dedicated module
  - PowerShell management support
  - Easy, customizable deployment (service installation, event log & performance counter creation, etc.)
  
##Orchard PowerShell

PowerShell CLI and provider for Orchard.

Requirement: make Orchard content and site management easily accessible from PowerShell scripts for automation purposes.

Use case: moving a ton of Sharepoint content into Orchard using just PowerShell scripts

**[Orchard PowerShell on CodePlex](https://orchardps.codeplex.com)**

###Main Features
 
  - PowerShell provider (including Orchard PSDrive)
  - Standard PowerShell cmdlets and extensibility features to provide custom cmdlets in your own modules
  - Integated cmdlet help
  - Support for all legacy (orchard.exe) commands
  - Support for running PowerShell scripts

###Examples

    //get all available Orchard cmdlets
    Get-OrchardPSCommand -All
	
    //execute the legacy "theme list" command to list all installed themes
    Invoke-OrchardCommand theme list /Summary:true
 
    //get all features of the default tenant
    Get-ChildItem .\\Tenants\Default\Features

    //enables all features starting with letter "a" on the current tenant
    Get-ChildItem a* | Enable-OrchardFeature

    //enables all orchard tenants that are currently disabled
    Get-Tenant -Disabled | Enable-Tenant
  
##Many, many more Proligence examples

**[Proligence on BitBucket](https://bitbucket.org/proligence)**

  - SignalR, Push Notifications
  - Service integration - SendGrid, New Relic
  - Issue tracking - YouTrack, JIRA
  - Virtual currency
  - Oculus Rift integration w/Orchard
  - ...
