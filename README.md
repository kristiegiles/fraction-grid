# fraction-grid 
This is a Sass partial you can use to generate a custom easy-to-use and infinitely scalable grid system. It uses [BEM syntax](https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
 and enforces a mobile-first approach. 
 
##Configuring the Grid##
Update the variables at the top of the _grid.scss file to configure your grid system.

`$columnsList`
A list of the column sizes you'd like. If you just want to start with a 12-column grid, you'd use
`$columnsList: '12'`. To add a 5-column option, you'd change it to `$columnsList: '12, 5.

To build the CSS using this repo, `cd` into the fraction-grid directory and run `npm install` and then `grunt`.

##Using the Grid##
###Grids###
The `grid` class should be used for groups of grid items. It's similar to a row in a traditional grid, but your grid items can span multiple rows. 

###Grid Items###
The `grid__item` class should be used for individual grid items (a.k.a. columns). Grid items must be direct decendants of a grid. 

###Width Utilities###
Grid items are 100% width by default. Sizing should be done with the `{columns}/{totalColumns}@{breakpoint}` utility classes – for example, `1/2@md 1/3@lg 1/4@xl` (or for a 12-column-only grid, you'd use `6/12@md 4/12@lg 3/12@xl`). These classes enforce a mobile-first approach and will affect viewports at the defined size and greater. 

```
<div class="grid">
    <div class="grid__item 1/2@md 1/3@xl"></div>
    <div class="grid__item 1/2@md 1/3@xl"></div>
    <div class="grid__item 1/2@md 1/3@xl"></div>
</div>
```
---
Rated for IE10+

Inspired by [Inuit CSS](https://github.com/csswizardry/inuit.css/) 
