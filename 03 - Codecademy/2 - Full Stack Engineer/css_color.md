# General
- *Named Colors*: English words that describe colors | Aka *Keyword colors* | ~140
- *RGB*: Numeric values that describe a mix of <u>red, green & blue</u> | $256\times 256\times 256=16.777.216$
- *HSL*: Numeric values that describe a mix of <u>hue, saturation & lightness</u>
- *Foreground Color*: Color that the element appears in | `color`
- *Background Color*: Color that the element's background appears in | `background-color`
---
- RGB color scheme is very close to how computers represent colors internally
## Hexadecimal
- Syntax used to specify colors
- *Hex colors*: Colors specified using this system
- Begins with hash character (`#`), followed by three/six characters
	- Characters represent values for <u>red, blue & green</u>
- Number system has 16 digits (0-15) instead of standard 10 (0-9)
	- 10-15 are represented by A-F
- All three char hex colors can be represented with six characters by repeating each char twice
	- `#0FF` => `00FFFF`
- Letters can be UPPERCASE or lowercase
## RGB
- Syntax used to specify colors in RGB values
- Use decimal numbers from 0-255
- `rgb(1, 2, 3)`
- Hex and RGB color representations are equivalent
## HSL
![[ColorWheel 1.svg|200]]
- Syntax:
	1. Degree of hue | 0-360
	2. Percentage of saturation (Intensity/Purity of color)
	3. Percentage of lightness (Brightness of color) | $0 = black$; $50 = normal$; $100 = white$
- `hsl(1, 2%, 3%)`
- Convenient for adjusting colors (In RGB it may affect all three color components)
- Useful for making a set of colors that work well together by selecting various colors that have same lightness & saturation but different hues
## Opacity & Alpha
- Only works with HSL, RGB & hex colors
- Add an a after `rgb` or `hsl` and a fourth value in the brackets
- *Alpha*: Fourth value in the brackets | 0-1 | $0=transparent$; $0.5=half-transparent$; $1=opaque$
	- "Amount of background to mix to foreground"
	- Blending happens for each pixel, no blurring
- `hsl(1, 2%, 3%)` -> `hsla(1, 2%, 3%, 0.4)`
- `rgb(1, 2, 3)` -> `rgba(1, 2, 3, 0.4)`
- `#FFFFFF`/`#FFF` -> `FFFFFF01`/`FFF1`
	- Hex opacity range: $00(transparent)-FF(opaque)$
	- Unconventional
- Zero opacity keyword:
	- `color: transparent;` == `rgba(0, 0, 0, 0)`