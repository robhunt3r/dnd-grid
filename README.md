# dnd-grid

This is a fork of [dattn/dnd-grid](https://github.com/dattn/dnd-grid).

I modified the layout algorithm to allow Box to be placed horizontally rather than vertically.

I modified subroutine `utils::moveBoxToFreePlace` to attempt to first place Boxes left to right to fill the Container's width
before jumping to a new line vertically.

The subroutine now needs the maximum width of the container which was added as a parameter to the function.
If the Container's width is set to Infinity, Boxes will be layed to the right of each other.

However, with a finite Container width, Boxes will nicely wrap to the next line when the first line is filled.

Pinned Boxes are left in place as before.

The ultimate goal is to only specify Box width and height and let the layout algorithm do its work of laying out non-pinned boxes.


Pierre M 29 Aug. 2018