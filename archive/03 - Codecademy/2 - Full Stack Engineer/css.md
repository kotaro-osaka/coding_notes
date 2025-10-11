# General
- "Cascading Style Sheets"
- Provides style to content of an HTML page (color, fonts, positioning, layout, etc.)
- Separate language from HTML due to computer science principle: *Separation of concerns*
	- Large codebases are kept maintainable by clearly differentiating problems to solve
- Default file name: `style.css`
- Link CSS & HTML file together:
```html
<link href="..." rel='stylesheet'>
```
## Anatomy
```css
<selector> { /*declaration block start*/
	<property>: <value>; /*declaration*/
} /*declaration block end*/
```
- Selector | Used to target element to be styled
- Declaration Block | Code in-between + `{}`curly braces that contains declarations
- Declaration | Group name for property + value that applies a style to selected element
	- Property | Signifies what visual characteristic of element is to be modified
	- Value | Signifies value of property
### Selector
- `*` | Universal selector
- Classes are used for reoccurring elements
- Ids are used for unique elements
- `type[attribute*=value]` | Selector for element attribute | Type can be omitted
- *Chaining*: E.g.: `element.class`
- *Descendant Combinator*: Select nested elements | E.g.: `.class element`
#### Pseudo-classes
- Examples: `:focus`; `:visited`; `:disabled`; `:active`
- Used to give user interaction, site navigation & position in document tree a different state
- Can be attached to any selector
- Syntax: `selector:pseudo-class`
## Visual Rules
- Font // typeface // font family
- Specified font must be installed on user's computer or downloaded with site
---
- Text-align:
	- `right`/`left`/`center`
	- `justify`: Spaces out text to align with right & left side of parent
- Opacity: Used to fade element | `0.5`: 50% visible
- Background-image: Set element's background to an image | Takes url or relative path
```css
background-image: url("image.jpg");
```
- `!important`: Used to override any style | Preferred when conflicted | Should never be used -> Unless: Working with multiple stylesheets // Bootstrap CSS framework
```css
p {
	color: blue !important;
}
```
