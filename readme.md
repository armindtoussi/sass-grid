# Sass Grid Readme

### Introduction
After having recently learned Sass, I wanted to build a project using my new knowledge; a way to solidify my knowledge in this language.  To that end I built a simple grid-system.  I used Bootstrap as a model for what I wanted to build.  I didn't copy it directly but more used the general mechanics of how the Bootstrap grid-system is used.  What i've ended up with is a light weight grid-system that is easy to use, and doesn't have the bloat that can come with frameworks.

There are some things that I opted out of doing for the time being such as column offsets and column pulls. 
###### Note - this is not properly tested nor would I say it is ready for production. Use with caution.

### How to Use
What we have here is a 12 column grid-system that is build using media queries with corresponding [screen sizes](https://github.com/armindtoussi/sass-grid#grid-classes). This system follows the model of having a container, and nesting rows within, and then nesting columns within the rows. I have opted to go with the `col-{size}-*` based class usage that Bootstrap uses because if it isn't broken, don't fix it. 
### Columns
All col classes start with `col-` and in the `{size}` portion goes the size, and sizes include: 
* xs - extra small screens
* sm - small screens
* md - medium screens
* lg - large screens
* xl - extra large screens 
For more information on screen sizes see [below](https://github.com/armindtoussi/sass-grid#grid-classes).

For the `*` section of `col-{size}-*`, you must include a number, and to avoid undefined behaviour, all cols should add up to 12 as this is a 12 column system.  

Example: 
```HTML
<div class="col-sm-6">content</div>
<div class="col-sm-6">content</div>
```
This will result in 2 columns of size 6 (or half the screen) that would collapse in to stacked full-width columns at small screen sizes.
Much like other grid-systems, we can combine column classes to get different behaviour at different screen sizes. 
```HTML
<div class="col-lg-6 col-md-4 col-sm-6"></div>
<div class="col-lg-6 col-md-4 col-sm-6"></div>
```
This will result in 2 columns of size 6 at larger screens or higher. When the screen size hits the medium breakpoint, it will turn into 2 columns of size 4 and when the screen size hits the small breakpoint, it will turn into 2 columns of size 6, until it hits the extra small screen size break point upon which all columns will stack. 

You can play around with column configurations and see what you can create.

### Containers 
Containers are built to contain rows and help control break points. There are 2 types of container. The standard `.container` or the full-width container `.container-wide`.  `.container` offers content centering and margin around the content based on screen size, and `.container-wide` offers a full-width fluid container. 

It is recommended that at least 1 container class is used as a parent to a row class. 

### Rows 
Rows are built to contain column classes. They have a negative margin on the left and right to compensate for padding of cols and containers. They are also given the clearfix as provided by [Nicolas Gallagher](http://nicolasgallagher.com/micro-clearfix-hack/) in order to compensate for floats using in column classes.  

Rows are to be nested inside a container class, and that rows wrap around column classes in order for the grid-system to work correctly. 

### Grid Classes

Class | Behaviour | Usage
----- | --------- | -----
.container | Auto Centered content, with margins around content | Used to contain rows
.container-wide | Full with container | Used to contain rows
.row | Applies a clearfix, and negative margins to compensate for row padding | Used to contain cols and is a child of containers
.col-{size}-* | Takes up the assigned number of columns until break point size is reached, then collapses to stacked full-width columns | Used to contain and layout content

### Breakpoints / Screen Sizes
Breakpoint | Screen Size | Variable Name | Gutter | Num Columns | 
---------- | ----------- | ------------- | ------ | ----------- |
 <576px    | mobile-sm   | $grid-xs      | 15px both sides | 12 |
 ≥576px   | mobile-lg   | $grid-sm      | 15px both sides | 12 |
 ≥768px   | tablet      | $grid-md      | 15px both sides | 12 |
 ≥992px   | tablet-lg   | $grid-lg      | 15px both sides | 12 |
 ≥1200px  | desktop     | $grid-xl      | 15px both sides | 12 |
 ≥1440px  | desktop-lg  | $grid-screen-max | 15px both sides | 12 |

## Extras 
#### Reset
I have applied a CSS reset to the grid-system using [Meyer Web's](http://meyerweb.com/eric/tools/css/reset/) standard CSS reset. 
#### Clearfix 
As previously mentioned, I use a clearfix mixin `@clearfix`. 


If you have any suggestions or corrections, fork and issue a pull request or create an issue. 

Thank you 

@armindtoussi
