# General
- `onCreate()`: Entry point to Android app | Similar to `main()` function in Kotlin
- `setContent()`: Used to define layout through composable functions
	- All functions with `@Composable` annotation can be called from `setContent()` or other Composable functions
	- `@Composable` annotation informs Kotlin compiler that function is used by Jetpack Compose to generate the UI
**Composable Function Syntax**:
```kotlin
@Composable // Added before function declaration
fun MyFunction(name: String, modifier: Modifier = Modifier) { // Composable function names are capitalized | Can't return anything
	Text(
		text = "MyText",
		modifier = modifier
	)
}
```
- Enable preview of composable by annotating it with `@Preview` & `@Composable`
	- `@Preview`: Informs Android Studio that composable should be shown in design view of file
		- Add a background to composable preview by setting parameter `showBackground` to `true`
			- Good for dark mode
---
## Change background color of Composable preview
- Text needs to be surrounded with a *Surface*
- *Surface*: Container that represents a section of UI where appearance can be altered
```kotlin
@Composable
fun MyFunction(name: String, modifier: Modifier = Modifier) {
	Surface(color = Color.Cyan) { // Select Color class' Cyan
		Text(
			text = "MyText",
			modifier = modifier
		)
	}
}
```
## Add Padding
⚠ For more scroll further down
- *Modifier*: Used to augment/decorate composable
	- Every composable should have optional parameter of type `Modifier`
Add padding:
```kotlin
@Composable
fun MyFunction(name: String, modifier: Modifier = Modifier) { // Optional Modifier of type Modifier
	Surface(color = Color.Cyan) { // Select Color class' Cyan
		Text(
			text = "MyText",
			modifier = modifier.padding(24.dp) // Add padding modifier
		)
	}
}
```
---
# Run app on Android Emulator
- *AVD*: Android Virtual Device
	- Software version | Emulator of mobile device that runs on computer & mimics config of particular type of Android device | Phone/tablet/TV/watch/Android auto device
- *Android Emulator*
	- Independent app used to set up virtual device
	- Has own system requirements
- Virtual Devices can use a lot of disk space
---
# Jetpack Compose
- Modern toolkit for building Android UIs
- UI Component is a function annotated with `@Composable`
	- Composable functions are immutable (can not be updated during runtime) | *Declarative UI*
	-> *Recomposition*: Reexecution of composable functions when app data changes
- *Annotations*
	- Used to attach extra information to code | Helps tools (Jetpack Compose compiler) & other devs understand app's code
	- Applied by prefixing name with `@` char at beginning of declaration to be annotated
	- *Annotations with parameters*
		- Provide extra information to tools processing them
		- Can pass multiple parameters to annotation
- *Compose function*
	- **Naming**
		- MUST be a noun: `DoneButton()`
		- NOT a verb or verb phrase: `DrawTextField()`
		- NOT a nouned preposition: `TextFieldWithLink()`
		- NOT an adjective: `Bright()`
		- NOT an adverb: `Outside()`
		- Nouns MAY be prefixed by descriptive adjectives: `RoundIcon()`
	- Must provide default values for any parameters to preview it
- *AndroidX (Android Extension) library*
	- Contains set of libraries & classes to provide core functionality
	- Accessible by using `androidx` package
- `sp`: Extension property for Int, which creates `sp` unit | `.sp` can be used in other data types
---
## Add images
- *Resource Manager*: Tool window, used to import, create, manage & use resources in app
- Scaling images based on different pixel densities can result in blurry images / Large images that consume too much memory / Not sized properly
	-> When resizing images that are larger than system can handle, <u>out-of-memory error</u> is thrown
- Placing images in `drawable-nodpi` folder stops resizing behavior
### Resources
- Additional files & static content that code uses
	- Bitmaps, user-interface strings, animation instructions, [etc.](https://developer.android.com/guide/topics/resources/providing-resources)
- Always separate app resources from code to maintain them independently
- Android uses appropriate resource based on current configuration | E.g.: Different UI layout based on screen size / Different strings based on language setting
#### Grouping
- Each type of resource should be placed in a specific subdirectory of project's `res/` directory | E.g.: `drawable/` for image resource / `mipmap/` for launcher icons / `values/` for string resources / [etc.](https://developer.android.com/guide/topics/resources/available-resources)
#### Accessing
- Resources can be accessed with resource IDs that are generated in project's `R` class
- `R` class: Automatically generated class by Android that contains IDs of all resources in project | In most cases ID is same as filename | E.g.: `R.drawable.<file>` => `R` class + Subdirectory in `res` folder + Resource `ID`
1. Assign call to `painterResource()` function with file resource as `arg` to a variable
`val <variable> = painterResource(R.<dir>.<file>)`
2. Add `Image` composable & pass `<variable>` as named argument for `painter`
`Image(painter = <variable>)`
3. Import: `import androidx.compose.foundation.Image`
- `painterResource()`: Loads drawable image resource & takes resource ID as argument
### Accessibility
- *TalkBack*: Google's screen reader
	- Integrated in Android devices
	- Gives users spoken feedback so users can use device without looking at screen
	- [more](https://developer.android.com/guide/topics/ui/accessibility/)
- `contentDescription` property: Used to define purpose of UI element => More usable with TalkBack
	- Can be set to `null` when element (E.g. image) only serves decorative purpose
---
## Layout
- Standard layout elements in Compose: `Column`, `Row` & `Box` composables
	- `Column`: Displays elements in Column (vertically)
		- `Modifier.align(alignment = Alignment.CenterHorizontally)`: Position child composable individually, defying parent alignment rules
	- `Row`: Displays elements in Row (horizontally)
	- `Box`
		- Used to stack elements on top of one another
		- Specific alignment of elements is configurable
### Layout Modifiers
- Used to position child elements using arrangement & alignment properties
- **Row**: `horizontalArrangement` & `verticalAlignment` arguments
- **Column**: `verticalArrangement` & `horizontalAlignment` arguments
- *Arrangement property*: Used to arrange child elements when size of layout is larger than sum of children
Column arrangement
![[VerticalArrangements.gif|350]]
Row arrangement
![[HorizontalArrangements.gif|500]]
---
## Scale Content
[Reference](https://developer.android.com/reference/kotlin/androidx/compose/ui/layout/ContentScale) | [Guide](https://developer.android.com/jetpack/compose/graphics/images/customize#content-scale)
`ContentScale` parameter: Used to adjust scale type of `Image`
`contentScale = ContentScale.<Type>`
- Requires `androidx.compose.ui.layout.ContentScale`
---
## Change Opacity
`alpha`: Used to adjust opacity with float value `F` (E.g. `0.5F`)
___
## Padding
`Modifier.padding`
![[Padding.png|250]]
All sides equal padding:
`Modifier.padding(16.dp)`
Specify side:
```kotlin
Modifier.padding(
	start = 16.dp,
	top = 16.dp,
	end = 16.dp,
	bottom = 16.dp
)
```
## Translation
- *Hardcoded String*: String that is written directly in the code of the app
	- Make it more difficult to translate app into other languages & reuse strings
- Strings can be extracted into resource file:
	- Name string resources in file
	- Use names as placeholders
	1. Select String without quotes
	2. Click bulb
	3. `Extract string resource`
	4. In `Extract Resource` dialog, adjust resource name
		- Lowercase name | Separate words with underscores (`_`)
	5. `OK`
	=> String replaced with `stringResource()` function | ⚠ If function is `getString()`, change!
	=> `stringResource(R.string.<resource_name>)` | Gets value from `/app/res/values/strings.xml`
