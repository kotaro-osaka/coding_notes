# General
- Concept to understand how elements are positioned & displayed
## Dimensions
> [!info] Property dimensions
> - `width`&`height`: The width & height of content area
> - `padding`: The amount of space between content area and border
> - `border`: The thickness & style of border surrounding content area & padding
> - `margin`: The amount of space between border and outside edge of element
>![[diagram-boxmodel_Updated_1-01.svg|500]]
- Pixels: Stay the same on all devices & overflow
**Height & Width**
- Default: Set to hold raw contents of box
**Min/Max Height & Width**
- `min-width`/`min-height`: Ensures a minimum width/height of element's box
- `max-width`/`max-height`: Ensures a maximum width/height of element's box
**Borders**
- `border: <width> <style> <color>;` | Values can be omitted as needed due to different argument types
- `width`: Thickness of border | Pixels or `thin`; `medium`; `thick`
- `style:` Design of border | [10 Different styles](https://developer.mozilla.org/en-US/docs/Web/CSS/border-style#Values) including `none`; `dotted`; `solid`
- `color`: Color of border
**Border Radius**
- Used to modify edges/roundness of element's border
- `border-radius` == Curvature that a circle with same value would have
- Create perfect circle:
	1. Set element's width & height to same value
	2. Set `border-radius` to `50%`
**Padding**
- Used to expand `background-color` & make content look less cramped
- Shorthand properties: `padding-top`; `padding-right`; `padding-bottom`; `padding-left`
	- 4 Values: `padding: 25px 50px 75px 100px;` => top | right | bottom | left
	- 3 Values: `padding: 25px 50px 75px;` => top | right & left | bottom
	- 2 Values: `padding: 25px 50px;` => top & bottom | left & right
	- 1 Value: `padding: 25px` => top, right, bottom, left
**Margin**
- Shorthand properties: `margin-top`; `margin-right`; `margin-bottom`; `margin-left`
	- 4 Values: `margin: 25px 50px 75px 100px;` => top | right | bottom | left
	- 3 Values: `margin: 25px 50px 75px;` => top | right & left | bottom
	- 2 Values: `margin: 25px 50px;` => top & bottom | left & right
	- 1 Value: `margin: 25px` => top, right, bottom, left
- `margin: auto`: Center element in containing element
	- Width must be set for containing element | Otherwise element will be set to full width
**Margin Collapse**
- Vertical margins collapse.
	- The larger margin sets the distance between elements.
- Horizontal margins do not collapse.
	- The sum of both margins equals the distance between elements.
**Overflow**
- `overflow` property controls what happens to content that overflows, because it's larger than its parent container
- Values:
	- `hidden`: Overflow content will be hidden from view
	- `scroll`: Scrollbar is added to element's box so the rest of the content can be viewed by scrolling
	- `visible`: Overflow content will be displayed outside parent element | *Default value*
	- [more](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)
## Resetting Defaults
- All major browsers have a default stylesheet | Used in absence of external stylesheet
	- Default stylesheet == *Agent stylesheet*
	- User agent == browser
- Have default CSS rules that set default values for <u>padding & margin</u>
- Reset:
```css
* {
	margin: 0;
	padding: 0;
}
```
## Visibility
- Used to hide elements from view with `visibility` property
- Values:
	- `hidden`: Hides an element
	- `visible`: Displays an element
	- `collapse`: Same affect as hidden, but exclusively used for tables & flex items to remove item & item's space
- Difference between `display: none` & `visibility: hidden`
	- Display completely removes element from page
	- Visibility makes element invisible, but reserves space for it
---
## Changing the Box
- Default:
	- Rendered width: Content width + Padding + Border
```css
* {
	box-sizing: content-box;
}
```
- Set default to `border-box`:
	- Rendered width: Content width (remaining width after subtracting padding & border)
```css
* {
	box-sizing: border-box;
}
```
## Position
- Block-level elements: Elements take up entire width of their parent by default
- Change default position:
	- `static`: Default
	- `relative`: Move element away, relative to default static position
		- `top`; `bottom`; `left`; `right`: *Offset properties*, used to move element away from default position
	- `absolute`: Ignored by other elements | Positioned relative to closest positioned parent | Can also be modified by *Offset properties*
	- `fixed`: Fix element to specific position | Can also be modified by *Offset properties*
	- `sticky`: Sticks element to specified position, even while scrolling | Can also be modified by *Offset properties*
- `z-index`: Accepts Integer Values | Controls how far back the element should appear on page (Control overlapping layers) | Doesn't work on static elements | Default: 0 (higher int => higher layer)
### Inline Display
- `display`: Value dictates if element can share horizontal space with other elements
	- `inline`: Box wraps tightly around content | Height & width cannot be specified in CSS doc
	- `block`: *Block-level* elements are not displayed in the same line as other elements (Fill in full width of parent)
	- `inline-block`: Elements can appear next to each other | Dimensions can be specified (width & height)
	- ![[display-inline-block.webp|300]]
- `float`: Used to offset element to far <u>right/left</u>
	- `clear`: Specifies how elements should react when they "bump" into each other
		- `left`: Left side of element will not touch any other element within same container
		- `right`: Right side of element will not touch any other element within same container
		- `both`: Neither side of element will touch any other element within same container
		- `none`: Element can touch either side