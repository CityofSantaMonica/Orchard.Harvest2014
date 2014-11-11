#From Bootstrap to Orchard

*Sebastien Ros*

[Youtube video](https://www.youtube.com/watch?v=gj5two6swwk)

> If you aren't using Bootstrap, you are doing it **wrong!** 

##Why Bootstrap?

  - Reset CSS
  - Typography: font sizes, relative sizes, spaces
  - Web UI design pattern: what components should be used, inventory of available components
  - Responsive
  - Consistency
  - Reusability
 
**The Real Reason**: because everyone uses it!

##Why a Bootstrap (Orchard) Theme?

  - Pull out Bootstrap assets automatically
  - Have a Bootstrap compatible layout
  - Make Bootstrap customizations easier
  - Let web developer apply their knowledge to Orchard
  - Make Orchard more appealing by default
  - Low friction base theme - easier to create new theme
  
###Why another Bootstrap Theme?

  - Existing
    - Lombiq - PGBT
	- Philip Senechal - PJS.Bootstrap
  - Different requirements
    - needed customizations not in any of the existing
	- needed different options
	- to be able to put it in the Core -> minimization dependencies
  - Not meant to be final

##Best Practices

  - Use the source code (LESS), not the compiled CSS
    - deploy your own compiled and minified CSS
	- fewer files to manage
	- can change variables
	- can use mixins
  - Don't change the Bootstrap source
