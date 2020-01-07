# Sass Grid Readme

### Introduction
After having recently learned Sass, I wanted to build a project using my new knowledge; a way to solidify my knowledge in this language.  To that end I built a simple grid-system.  I used Bootstrap as a model for what I wanted to build.  I didn't copy it directly but more used the general mechanics of how the Bootstrap grid-system is used.  What i've ended up with is a light weight grid-system that is easy to use, and doesn't have the bloat that can come with frameworks.

There are some things that I opted out of doing for the time being such as column offsets and column pulls. 
###### Note - this is not properly tested nor would I say it is ready for production. Use with caution.

### How to Use
What we have here is a 12 column grid system that is build using media queries with corresponding screen sizes (#see below link). This system follows the model of having a container, and nesting rows within, and then nesting columns within the rows. I have opted to go with the ```col-{size}-*``` based class usage that Bootstrap uses because if it isn't broken, don't fix it. 

All col classes start with ```col-``` and in the ```{size}``` goes the size. sizes include: 
* xs - extra small screens
* sm - small screens
* md - medium screens
* lg - large screens
* xl - extra large screens 
For more information on screen sizes see below(add a link here).

For the * section of ```col-{size}-*```, you must include a number, and to avoid undefined behaviour, all cols should add up to 12 as this is a 12 column system.  

Example: 
```
<div class="col-sm-6">content</div>
<div class="col-sm-6">content</div>
```
This will result in 2 columns of size 6 (or half the screen) that would collapse in to stacked full-width columns at small screen sizes. 

#### Containers 


### Grid Classes

Class | Behaviour | Usage
----- | --------- | -----
.container | Auto Centered content, with margins around content | Used to contain rows
.container-wide | Full with container | Used to contain rows
.row | Applies a clearfix, and negative margins to compensate for row padding | Used to contain cols and is a child of containers
.col-{size}-* 