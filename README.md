# fraction-grid #

##Configuring the Grid##
Update the variables at the top of the _grid.scss file to configure your grid system.

`$columnsList`
A list of the column sizes you'd like. If you only want a 12-column grid, you'd just use
`$columnsList: '12'`. To add a 5-column option, you'd change it to `$columnsList: '12, 5'`

Then, `cd` into the fraction-grid directory and run `npm install` and then `grunt` to build your CSS.

##Using the Grid##
###Grids###
The `grid` class should be used for groups of grid items. It's similar to a row in a traditional grid, but your grid items can span multiple rows. 

###Grid Items###
The `grid__item` class should be used for individual grid items (a.k.a. columns). 

###Grid Item Sizing###
Grid items are 100% width by default. Sizing should be done with the `{columns}/{totalColumns}@{breakpoint}` classes – for example, `1/2@md 1/3@lg 1/4@xl`. For a 12-column-only grid, you'd use `6/12@md 4/12@lg 3/12@xl`.  

