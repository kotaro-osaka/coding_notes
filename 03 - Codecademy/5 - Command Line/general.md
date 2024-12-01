#command_line

# Info
- *Text interface* for computer's operating system - fully text-based
- Used to traverse and edit *file system*
- **Create**, **edit**, **delete** files & more
- Mac & Linux -> Access through *Bash*(CLI)
- Takes in commands and passes them onto OS to run
### Bash - CLI
- *"Bourne-Again Shell"*
- Open Source
- Created *1989* by *Brian Fox* as a free software replacement for the *Bourne Shell*
- **Shell**: Specific kind of CLI
- Default shell for Linux & Mac
- Most used & widely distributed
#### Bash on Windows
- Install program *Git Bash*(Git for Windows)
## Navigation
- View contents of file system
- Move through different directories(folders)
- Create new files & directories
## Manipulation
- Move files
- Delete files and directories
## Redirection
- Redirect standard *input*, *output* & *error messages*
- Display contents of a file
- Write to a file
- Search through directories
## Advantages
- Run programs
- Write scripts to automate common tasks
- Combine simple commands to handle difficult tasks
---
## File System
- Organizes computer’s files and directories into a *tree structure*
![[IMG FilesystemVSFIlemanagerGI.png|1000]]
- `root directory`: First directory in file system, Parent of all other directories & files in the file system
- *Parent-Child relationship*: Continues as long as directories and files are *nested*
- *Parent directories*: Can contain more *child directories* & *files*
- *Current directory* = *Working directory*
- *Relative Path*: `/`-separated list of all directories leading to goal directory in relation to <u>current working directory</u>
- *Absolute Path*: `/`-separated list of all directories leading to goat directory <u>from root directory or drive</u>
---
- *Options*: Modify behavior of commands
- `.bak`: File extension, commonly used to notate file as a *backup of file with same name*
- *Wildcards*: Special characters
---
- *Standard Input*: `stdin`: Information inputted into terminal through input device
- *Standard Output*: `stdout`: Information outputted after process is run
- *Standard Error*: `stderr`: Error message outputted by failed process
- *Redirection*: Reroutes standard input/output/error to/from a different location
- `|`: *Pipe*: "Command to command"
## Environment
`/bin`: Stores commands as scripts
### nano
- Command line text editor
- Only accepts keyboard input
- `^` = `ctrl`
### .bash_profile
- File used to store environment settings for terminal
- File is the home directory
- Accessible by name *.bash_profile*
- At start of session bash profile is executed before commands
- `.`: Indicates *hidden file*
- Add commands to be executed with new terminal session
- *Environment Variables*: Variables that can be *used across commands & programs* and *hold information about environment*