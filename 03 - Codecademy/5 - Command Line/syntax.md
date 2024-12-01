# General
`$`: *Shell Prompt*, Appears when terminal is ready to accept a command
`$`: Also used to return *variable's value*
```bash
// Example
echo $USER
```
## Commands
- `history`: *Lists* history of used commands in session
### Navigation
- `ls`: *Lists* all directories and files in current directory
- `pwd`: *"Print Working Directory"*, Outputs name of working directory#
- `cd`: *"Change Directory"*, Change working directory
- `mkdir`: *"Make Directory"*, Create new directory in working directory, *Argument*: New directory name **or** Relative path
- `touch`: Create *new file* in working directory, *Argument*: New file name + File extension
### Manipulation
- `cat`: *Outputs contents* of specified file
- `cp`: *Copies* files/directories from <u>source to destination</u>
- `mv`: *Moves* files without making a copy from <u>source to destination</u>, *Rename* file by moving file to renamed file, not directory
- `rm`: *Deletes* files/directories <u>permanently</u>
### Redirection
- `echo`: *Print* inputted string to terminal **or** *redirect* input to file
- `>`: Redirects output to file and *overwrites* it's contents
- `>>`: Appends(adds) output to file
- `<`: Inputs input into command
- `|`: Passes output of command as input to another
- `wc`: Outputs number of *lines*, *words* & *characters*
- `sort`: Orders input alphabetically for standard output
- `uniq`: *"Unique"*, Filters out *adjacent, duplicate* lines in file
- `grep`: *"Global Regular Expression Print"*, Searches files for lines that *match a pattern*, Case sensitive
- `sed`: *"Stream Editor"*, Modifies input based on expression, *"Find and Replace"*
```bash
sed 's/searchedString/replacementString/' file
// s = "substitution"
// FIRST instance
sed 's/searchedString/replacementString/g' file
// g = "global"
// ALL instances
```
### Environment
- `env`: *"Environment"*, Returns list of *environment variables* for current user
```bash
// Example: Select value of env. variable
env | grep PATH
// env is searched through by grep for PATH (same as echo $PATH)
```
#### nano - Command line text editor
- `nano newFile`: *Create* new file & open
- `ctrl + O`: *Save* file
- `ctrl + X`: *Exit* nano
- `ctrl + G`: Open *help* menu
##### .bash_profile
- `nano .bash_profile`: *Open* and *edit* bash profile in *customization/*
- `sourche .bash_profile`: Make changes available
- `alias`: Create *keyboard shortcuts* or aliases for commonly used commands
```bash
// Examples
alias pd="pwd"
alias ll="ls -la"
```
- `export`: Makes variable available to all child sessions initiated from current session (Variable persists across programs)
---
## Helper Commands
- `tab`-key: Autocomplete command
- `up`/`down`-key: Cycle through previously used commands
- `clear`: Clear terminal
---
## Arguments
- `.`: Working directory
- `..`: Directory above working directory
```bash
// Move up 2 directories
cd ../..
// Move to adjacent directory
cd ../directory_name
```
---
## Options
### `ls`
- `-a`: Display files that start with a dot, which are normally hidden
- `-l`: List all contents of directory in long format with file permissions
	- Lists as table with 7 columns
	1. *Access rights*: Indicate <u>read, write & execute</u> permissions on file or directory allowed to <u>owner, group & all users</u>
	2. *Number of hard links*: Represents number of hard links to file/directory, Includes parent directory link & working directory link
	3. *Username* of file's owner
	4. *Name of group* that owns file
	5. *Size* of file in bytes
	6. *Date & Time* that file was last modified
	7. *Name* of file/directory
- `-t`: Order directories and files by time they were last modified
- `-alt`: **Example** combination of options
### `rm`
- `-r`: *Delete* directory & all children <u>permanently</u>
### `grep`
- `-i`: Enables command to be *case insensitive*
- `-R`: *"Recursive"*, Searches all files in directory, Outputs *filenames & lines* containing matched results
- `-Rl`: *"Files With Matches"*, Searches all files in directory, Outputs filenames with matched *results without lines*
### `sed`
- `-i`: Rewrite file, not just command line output
---
## Wildcards
- `*`: Select *all* files from working directory
	- Specify file name with *prefix*/*suffix* filter
---
## Variables
### Environment Variables
- `USER`: Computer's user
- `PS1`: Defines *makeup and style* of command prompt
- `HOME`: Displays path of *home directory* `~`
- `PATH`: Stores *list of directories* separated by a colon, Lists which directories contain *scripts for command line* to execute
# Useful
1. Change default command prompt `$`
	- `export PS1=">> "`: Changes `$` to `>>`, Leave space for aesthetics
![[BashToWinCommands.png|750]]
- Open directory in VS Code:
	1. Change to directory
	2. Type `code .