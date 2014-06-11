#Core Contributors Panel and Q&A

*Bertrand, Sebastien, Sipke, Piotr*

> **Where is the project now?**

> **Piotr:** I use Orchard in almost every project...I have real faith in the future.
> **Sipke:** Started as a love-hate relationship...but even today, I find out about new stuff.
> **Sebastien:** I am Orchard! It's a beautiful project.

> **Where does Orchard stop [today]?

> **Sipke:** I don't see it.
> **Bertrand:** There are limitation of course. You need to be responsible engineer, know your tools. More and more, Orchard is a framework.

> **CMS vs. Framework?**

> **Sipke:** If I started with vanilla MVC, the first thing I would do is implement a module system. 
> **Bertrand:** I'm working on non-Orchard projects, and find myself re-implementing some of the features that are figured out in Orchard.
> **Piotr:** Don't have to use all the modules

> **What are Orchard's weaknesses? Compared to other CMS?**

> **Bertrand:** Both a strength and weakness - because it is conceptually abstract, difficult to learn. Platform is definitely difficult for beginners. Best comparison you can make is Drupal, *most of the concepts come from Drupal*. Something like WordPress...easy to use, easy to learn, have to "sign a pact with the Devil", encourages [bad development practices] you shouldn't.
> **Piotr:** Orchard has it's own concepts, you have do things "the Orchard way", this can be considered a limitation. Modularity is a strength, but also a weakness due to the amount of modules [in core]. Alot of flexibility, but makes the site bigger, slower.
> **Bertrand:** Things can be a little disconnected because of the modularity. Something we can and should address in next versions.
> **Sipke:** Steep learning curve can be downside, easily mitigated by *you the community* writing blog posts, posting videos, etc. But when I started with Orchard, I became a much better developer. 
> **Sebastien:** Main strength is the community, it's you! 

> **How do you see the Roslyn [C# compiler] coming into play?**

> **Bertrand:** Removing code!

> **Are you looking to bring the separate solutions [standard/Azure] together?**

> **Sebastien:** Today, you can use the standard solution; no good reason to use the Azure solution. The right method these days is to use Azure websites [as opposed to Cloud Services]. 

> **Upgrading sites to the newest version seems to be painful. E.g. getting latest security/bug-fixes**

> **Sebastien:** minor versions have no breaking-changes. Theoretically possible to do upgrades (full files replace) within Orchard, e.g. as NuGet package of entire Orchard src
> **Piotr:** Easily doable from technical standpoint when we have a new Gallery. That will be part of the process.

> **How do you have your own feed of modules?**

> **Sebastien:** Gallery settings. But you need a feed server, that is a pain to setup. 

> **Fully async module, any side-effects?**

> **Sebastien:** Everything should work, if you are on 4.5. Nothing special. 

> **How do you determine content item vs. stored externally vs. stored in regular SQL table**

> **Sebastien:** sometimes you want everything to be a content item, a lot of built in functionality. But there is a lot of overhead for simple data. E.g. AuditTrailRecord will not be a content item, because it only needs to be stored (not edited).
> **Bertrand:** it is very tempting to make everything a content item. But the real question is semantic: Is is a content item in a more semantic sense. You shouldn't just base the decision on convenience, but on whether it is the right thing to do. 

> **Do you envision incorporating some of the async stuff into the e.g. content management pipeline, shape building pipeline?"

> **Sebastien:** I'm not very good at async/await, so I don't think so.

> **Suggestions on how to start contributing to source? How is everyone liking the move to Git?**

> **Bertrand:** Really 2 ways to start - try to create your own modules, take active bugs and dig into them. The way I learned on the platform is by fixing bugs and answering questions on the forums. 
> **Piotr:** Writing your own module, making it public. Troubleshooting - jumping through the code, the hard way is the best way!
> **Bertrand:** I'm super happy on Git. Mercurial cohabitates with Git just fine.
> **Piotr:** I hated Git before, because I didn't know it. Now, I won't go back to any other SCM.

> **Do I implement a search feature using Projections or Lucene?**

> **Sipke:** If you have thousands of items, use Lucene because of the index. Can use multiple indices.
> **Sebastien:** Index can be corrupted (file-system based), less risky to use content manager API to do queries.
