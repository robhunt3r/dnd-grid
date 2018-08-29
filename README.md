# dnd-grid

This is a fork of [dattn/dnd-grid](https://github.com/dattn/dnd-grid).

I modified the layout algorithm to allow Boxes to be placed horizontally rather than vertically.

I modified subroutine `utils::moveBoxToFreePlace` to attempt to first place Boxes left to right to fill the Container's width
before jumping to a new line vertically.

The subroutine now needs the maximum width of the container which was added as a parameter to the function.
If the Container's width is set to Infinity, Boxes will be layed to the right of each other to Infinity and beyond.

However, with a finite Container width, Boxes will nicely wrap to the next line when the first line is filled.

Pinned Boxes are left in place as before.

The ultimate goal is to only specify Boxes widths and heights and let the layout algorithm do its work of laying out non-pinned boxes.
This is particularly useful for dashboard-type layout where use simply add dashboard widgets that nicely get layed out by dnd-grid.
Of course, this new algorithm is also kicked in when moving box around (i.e. it first attempts to place boxes to the right of the moving Box).


Pierre M 29 Aug. 2018