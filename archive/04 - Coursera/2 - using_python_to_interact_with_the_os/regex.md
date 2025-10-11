# Regex
___
> Regular expressions allow us to search a text for strings matching a specific pattern.
## Special Characters
- `*` Any amount of times
- `.` Wildcard, can be replaced with any other char
	- `.*` Repeated matches, matches any character [[#^ce86a3|repeated as many times as possible]] (incl. 0)
- `^` Caret/Circumflex, indicates to search for matching substrings at beginning of a line
	- `[^]` Exclude character from search
- `$` Indicates to search for matching substrings at end of a line
- `+` Matches one or more occurrences of the character that comes before it
- `?` Mark prefixed character as optional
- `\` Escape Character
- `\w` Alpha-numeric characters
- `\d` Matches digits
- `\s` Matching whitespace characters
## Concepts
- **Greedy** ^ce86a3
	- Special quantifiers define how many times a subpattern can match within searched text
## Grep
> Command line regex tool
- `$ grep word /path_to_file` returns matching words with highlighted substrings *case sensitive*
- `$ grep -i word /path_to_file` *non-case-sensitive*
## re module
`import re`
- `r"abc"` Rawstring, back slashes are treated as normal characters *always use for regex*
- `r"[Aa]pp"` Allow lower/upper case
- `r"[a-z]pp"` Define range of letters, Works with uppercase and digits `[a-zA-Z0-9]`
- `r"a|b"` Search for substring a or b
___
- `re.search(regex, String)` Returns `Match` object with position and match of *first* or `None`
	- `re.search(regex, String, re.IGNORECASE)` Ignore lower/upper case
- `re.findall(regex, String)` Returns list of all matches