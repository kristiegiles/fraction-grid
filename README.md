# fraction-grid 
Grid systems that use class names like `col-md-3` don't give you the ability to change the number of columns in your grid without refactoring your whole codebase. 

This is a Sass partial you can customize to generate your own easy-to-use and infinitely scalable grid system. It uses [BEM syntax](https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
 and enforces a mobile-first approach. 
 
##Configuring the Grid##
Update the variables at the top of the _grid.scss file to configure your grid system.

###`$columnsList`###
A list of the column sizes you'd like. If you just want to start with a 12-column grid, you'd use
`$columnsList: '12'`. To add a 5-column option, you'd change it to `$columnsList: '12, 5'`.

###`$vr-border-style`###
Style to use for vertical rules.

###`$gutter-size`###
Space between grid items.

###`$breakpointsList`###
Namespaces for your breakpoints.

###Breakpoint Sizes###
You can change the pixel values on these. If you choose to add or remove breakpoints, you must update the `$breakpointsList` to match. 
```
$breakpoint-sm
$breakpoint-md
$breakpoint-lg
$breakpoint-xl
```

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

For columns that are the same sizes at all breakpoints, just leave off the `@{breakpoint}` part. 
```
<div class="grid">
    <div class="grid__item 1/2"></div>
    <div class="grid__item 1/2"></div>
</div>
```

###Vertical Rules###
To add a vertical rule, use the `vr-right` or `vr-left` classes on a grid item. To add a vertical rule only at a specified breakpoint and larger, use `vr-right@{breakpoint}` or `vr-left@{breakpoint}`. The vertical rule will be the height of the tallest grid item in the row. 
```
<div class="grid">
    <div class="grid__item 1/3@md vr-right@md"></div>
    <div class="grid__item 2/3@md"></div>
</div>
```

###Spacing Utilities###
You may often want bottom margins that match the gutter width of your grid items. You can add these with the `spacing-bottom` / `spacing-bottom@{breakpoint}` utilities. 
```
<div class="grid">
    <div class="grid__item 1/3@md 1/3@xl spacing-bottom"></div>
    <div class="grid__item 1/2@md 1/3@xl spacing-bottom"></div>
    <div class="grid__item 1/2@md 1/3@xl spacing-bottom"><div>
    <div class="grid__item 1/3@md 1/3@xl spacing-bottom"></div>
    <div class="grid__item 1/2@md 1/3@xl spacing-bottom"></div>
    <div class="grid__item 1/2@md 1/3@xl spacing-bottom"><div>
</div>
```

---
Rated for IE10+

Inspired by [Inuit CSS](https://github.com/csswizardry/inuit.css/) 
