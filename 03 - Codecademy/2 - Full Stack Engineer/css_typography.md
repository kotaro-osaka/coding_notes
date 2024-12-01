# General
- *Web Safe Fonts*: Fonts that will appear same across all browsers & OS | Full list [here](https://www.cssfontstack.com/)
- *Font Stacks*: Group of fonts | Usually contains list of similar looking fonts
- *Fallback Fonts*: Used when preferred font is not available
	- `font-family: Caslon, Georgia, 'Times New Roman';`
## Serif & Sans-Serif
- Serif: Extra details on ends of each letter
- Sans-Serif: Doesn't have extra details\
- Can be added as a final fallback font:
	- `font-family: Caslon, Georgia, 'Times New Roman', serif;`
![[htmlcss1-diagram__fontanatomy.svg|500]]
## Font Weight
`font-weight`
- Specifies how thin/thick text appears
- *Keyword Values*:
	- `bold`: Bold font weight | Equal to $700$
	- `normal`: Normal font weight | Default | Equal to $400$
	- `lighter`: One font weight lighter than element's parent value
	- `bolder`: One font weight bolder than element's parent value
- *Numerical Values*: $1(lightest)-1000(boldest)$ | Common practice to use in increments of $100$
	- Not all fonts can be assigned a numeric font weight
	- Not all font weights are available to all fonts
## Font Style
`font-style`
- Used to change text appearance
- *Property Values*

| Value   | Description                                       |
| ------- | ------------------------------------------------- |
| normal  | Browser displays normal font style &#124; Default |
| italic  | Browser displays italic font style                |
| oblique | Browser displays oblique font style               |
| initial | Sets property to default value                    |
| inherit | Inherits property from parent element             | 
## Text Transformation
`text-transform`
- Used to style text to appear all `UPPERCASE` or `lowercase`
- Use case: News website that always wants breaking news headers to display in all uppercase
## Text Layout
- Display & Layout of text within element's container
- `em` units are useful for spacing based on size of font (Relative)
### Letter Spacing
`letter-spacing`
- Used to set horizontal spacing between chars
- Not common use, but can improve readability of fonts/styles
- Takes length values in `px` or `em`
### Word Spacing
`word-spacing`
- Used to set horizontal spacing between words
- Not common use, but can enhance readability of bolded/enlarged text
- Takes length values in `px` or `em`
### Line Height
`line-height`
![[LineHeight.png|500]]
- Used to set height of line containing text
- Takes unitless numbers (`1.2`), `px`, `%`, or `em`
- Unitless value if preferred, because it's based on current font size (Relative)
### Text Alignement
`text-align`
- Used to align text to parent element
- [more](css.md)
## Web Fonts
- Fonts used for own website
- Limitless
- Font hosts: Google Fonts, Adobe Fonts
	- Include by linking from HTML document with `<link>` element
### Web Fonts Using <link>
1. Select font
2. Select styles available for font
3. `<link>` element is automatically generated from website
4. `<link>` can be integrated in the head of HTML document
5. Create `font-family` declarations in CSS document
### Web Fonts Using @font-face
- Downloaded from website & integrated in document like normal file
- File formats:
	- OTF (OpenType Font)
	- TTF (TrueType Font)
	- WOFF (Web Open Font Format)
	- WOFF2 (Web Open Font Format 2) | Most progressive
- Should include TTF, WOFF & WOFF2 formats with `@font-face` rule to ensure compatibility with browsers
```css
@font-face {
	font-family: 'CustomFontFamilyName';
	src: url('/pathToFile') format('woff2'),
		 url('/pathToFile') format('woff'),
		 url('/pathToFile') format('truetype');
}
```
- `@font-face`: Recommended to define at top if CSS stylesheet
- `font-family`: Used to set custom name for downloaded font
- `src`: Contains values of relative paths to font files + formats
	- Ordering of files is order the browser will search in, for supported file type