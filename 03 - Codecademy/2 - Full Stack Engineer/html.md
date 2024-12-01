# General
- "Skeleton" of a web page
- Provides structure to the content (text, images, buttons, videos, etc.)
- "Hypertext markup language"
---
## Markup
- *Markup*: Annotating text that is distinguishable from the text itself
- HTML separates content and annotation by using tags
---
## Elements
- Tags are "markup" for HTML
- Annotations that provide information about type of content that is contained
---
## Hypertext
- Text that is linked to other text
- Hyper indicates that text expands beyond traditional constraints of the written word
---
### Hyperlinks
- `href`: "Hyperlink reference"
- `<a>`: "Anchor" tag
---
### Document
- `<!DOCTYPE html>`: Tells browser what type of document to expect + version (HTML5)
- Saved in `.html` file
- `<html>` Tag: Anything between the tags is interpreted as HTML code
#### Head
- `<head>`: Contains metadata for web page
- *Metadata*: Information about the page that isn't directly on the web page
#### Title
- `<title>`: Displayed in browser tab's text
#### Links
- Open link in new tab: `<a href="..." target="_blank">`
- Use relative file path for internal links: `<a href="./path">`
	- `./`: Working directory
- Use `#`ids to link to targets on same page
---
- Special symbols must be "escaped" and placed in `[]`brackets
#### Tables
```html
<table>
	<tbody>
		<tr>
			<th></th>
			<td></td>
		</tr>
	</tbody>
</table>
```
- `<table>`: Holds contents of table
- `<thead>`: Contains all `<th>`
- `<tbody>`: Contains all of table's data
- `<tr>`: "Table row" | Inside `<table>`
- `<th>`: "Table heading" | Inside `<tr>`
	- `scope="row"`: Specifies that heading is for a row
	- `scope="col"`: Specifies that heading is for a column
- `<td>`: "Table data" | Inside `<tr>`
	- `colspan="numOfColumns"`: Span data across columns
	- `rowspan="numOfRows"`: Span data across rows
- `<tfoot>`: Contains table's footer
## Semantic HTML
- "Semantic" = 'related to meaning'
- Semantic elements provide information about content between `<>` & `</>`
- Used to select HTML elements based on their meaning, not how they're presented
- **Accessibility**:
	- Make webpages accessible for mobile & for people with disabilities
	- Screen readers & browsers are able to interpret semantic code better
- **SEO**:
	- Improves "Search Engine Optimization" => Increase in number of webpage's visitors
	- Search engines are better able to identify & weight content
- Improves source code readability
### Examples:
- `<header>`
- `<nav>` | Navigation
- `<main>` | Dominant content
- `<footer>`
	- Contact/Copyright info
	- TOS (Terms of use)
	- Site Map
	- Reference to top of page links
- `<section>` | Elements in a document: Chapters/Headings/...
- `<article>` | Holds content that makes sense on its own | Articles/Blogs/Comments/Magazines/...
	- Helps screen reader understand relative positioning of content
- `<aside>` | Marks additional info that can enhance another element but isn't required to unterstand main content
- `<figure>` | Used to encapsulate media (image/illustration/diagram/code snippet/...) which is referenced in main flow of document
- `<figcaption>` | Used to describe media in `<figure>` | Usually placed in `<figure>`
- **Audio** [Useful attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio#Attributes):
```html
<audio autoplay controls>
	<source src=".mp3" type="audio/mp3">
</audio>
```
- **Video**:
```html
<video src=".mp4.gif" controls autoplay loop>Default text</video>
```
- `<embed src="..." />` | Used to embed video/audio/gifs from external source