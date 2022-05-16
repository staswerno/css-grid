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

## special units and functions

### fractional units

“portion of the remaining space”
1fr 3fr is essentially 25% 75% (excluding padding etc)

### sizing keywords

for sizing rows and columns

- min-content: the minimum size of the content. Imagine a line of text like “E pluribus unum”, the min-content is likely the width of the word “pluribus”.
- max-content: the maximum size of the content. Imagine the sentence above, the max-content is the length of the whole sentence.
- auto: this keyword is a lot like fr units, except that they “lose” the fight in sizing against fr units when allocating the remaining space.
- fit-content: use the space available, but never less than min-content and never more than max-content.
- fractional units: see above

### minmax function

e.g.
grid-template-columns: minmax(10px, 1fr) 3fr;
this is actually a preferred default setting
"you want minmax(10px, 1fr) not 1fr"
source: https://css-tricks.com/you-want-minmax10px-1fr-not-1fr/

### the repeat() function and keywords

grid-template-columns:
1fr 1fr 1fr 1fr 1fr 1fr 1fr 1fr;

/_ easier: _/
grid-template-columns:
repeat(8, 1fr);

/_ especially when: _/
grid-template-columns:
repeat(8, minmax(10px, 1fr));

good with keywords:

auto-fill: Fit as many possible columns as possible on a row, even if they are empty.
auto-fit: Fit whatever columns there are into the space. Prefer expanding columns to fill space rather than empty columns.

This bears the most famous snippet in all of CSS Grid and one of the all-time great CSS tricks [https://css-tricks.com/books/greatest-css-tricks/flexible-grids/]:

grid-template-columns:
repeat(auto-fit, minmax(250px, 1fr));
The difference between the keywords is spelled out in detail here.

### masonry and subgrid

look into these later
