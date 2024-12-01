# Primary vs. Secondary navigation
| Primary                                                                                         | Secondary                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Contains most important links & buttons that need to be displayed on **every** page of the site | "Breadcrumb navigation"<br>Consists of clickable list of pages/attributes that led to current page<br>Helps User understand the extent of the site & current location<br>![[UI_breadcrumb.svg]] |
## Benefits of breadcrumbs
- Users that enter a random page can quickly get an overview and understand where they are located
- Hints to extent of the site
- Provide way for user to quickly jump backward in their navigation
- Use of breadcrumbs is a judgement call depending on type, depth, complexity of site
---
# Breadcrumbs
- Typically displayed `inline` & take up minimal space
- Located in header, left-aligned, below primary navigation
- Separated by `>` / `/`
- Display separation symbols automatically with CSS:
```css
.breadcrumb li+li::before {
	content: ">"; /*Symbol*/
}
/*
`+`:
"Adjacent sibling combinator",
only selects 2 elements when directly next to each other with same parent,
Second element of pair gets selected
`::before`:
Creates pseudo-element,
Often used with `content` property to add content to be displayed `before` selected element (`li`)
*/
```
- Often not underlined
	- Underlines are used to communicate that text within paragraph elements can be clicked
	-> Users are supposed to recognize breadcrumbs as part of site nav, rather than clickable text
- Should highlight on hover to indicate clickability
- Not primary way users will navigate a site
	- Don't make breadcrumbs only nav structure
- No reason to include breadcrumbs if site contains few pages and breadcrumbs are available through primary navigation
## Breadcrumb Types
- Location
	- Based on location with respect to navigation structure of website
- Attribute
	- Based on attributes of page or product being browsed
- Path
	- Based on user's unique path through site
	- Large steps can be shortened by abbreviating first: `... > About > Register`
	- Needs to have compelling reason to implement