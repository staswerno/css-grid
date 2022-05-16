# css grid notes

source: https://css-tricks.com/snippets/css/complete-guide-grid/

- two dimensional grid layout system (vs flexbox which is one dimensional)
- can work well together with flexbox

1. define a container element as a grid with display: grid
2. set the column and row sizes with grid-template-columns and grid-template-rows
3. place its child elements into the grid with grid-column and grid-row

item source order doesn't matter - css places them, so grid can be rearranged with media queries

float, display: inline-block, display: table-cell, vertical-align and column-\* properties have no effect on a grid item

## terminology

- Grid Container: element on which display: grid is applied / direct parent of all the grid items
- Grid Item: children (i.e. direct descendants(!)) of the grid container
- Grid Line: dividing lines that make up the structure of the grid / can be either vertical (“column grid lines”) or horizontal (“row grid lines”)
- Grid Cell: space between two adjacent row and two adjacent column grid lines / a single “unit” of the grid
- Grid Track: space between two adjacent grid lines / the columns or rows of the grid
- Grid Area: total space surrounded by four grid lines / may be composed of any number of grid cells
