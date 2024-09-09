# Remote Access
Often necessary to access a server over a network
1. The system may have no keyboard or monitor
	- Usually don't need them because we can access the server over a network instead
2. The system may be shared between multiple users
3. The system may not bew physically accessible

1. Open cmd
2. `ssh [username]@fran.mta.ca`
3. Type password

# Basic Terminology
`Working Directory`
- Current position in the file system
- `.` as a shorthand

`Parent Directory`
- Directory that **contains** a certain directory
- `..` as shortcut

`Home Directory`
- Directory for user's own files
	- Freely editable in own, but not in other's
- Many programs runnable are stored in system directories like `/bin`
- `"~"` as a shorthand
	- `~user`: user's home directory

`Permission`
- The way files outside of the home directory are protected

# Commands

$\rightarrow$ To find the information about a certain command: `man <Command>`

## Basics

Moving around the file system
- `pwd`: [P]rints the current [W]orking [D]irectory. 
- `cd`: [C]hanges the working [D]irectory
- `ls`: [L]i[S]ts files and subdirectories
- `echo`: Print something(like variable) to the terminal

Managing files and directories: 
- `less`: Display the contents of a text file with the ability to scroll through the contents. 
- `cp`: [C]o[P]ies one or more files to a new directory. 
- `mv`: [M]o[V]es a file.
- `chmod`: [CH]anges [MOD]e (permissions) of a file or directory. 
- `rm`: [R]e[M]oves (deletes) one or more files. 
	- Permanent and irreversible. Use with extreme caution! 
- `mkdir`: [M]a[K]es a new [DIR]ectory 
- `rmdir`: [R]e[M]oves a [DIR]ectory. 
	- Permanent and irreversible. Use with extreme caution! By default only works on empty directories.

Examining and Editing Files
- `cmp`: Compare two files to see if they're identical
- `diff`: Print the difference between two files
- `head/tail`: show first/last N lines of a file
- `more`: Show more of a files
- `less`: Similar to `more`, but with more options
- `grep`: Search within a file(Go to Regular Expression and Print)
- `nano/pico`: Basic but easy to use text editor

### `grep`
`grep [options] <Expression> file [ file ... ]`
- Without options, it find line matching the `<expression> (Regular Expression)` in the list of files indicated, and prints any matching lines out
- Options
	- `-v`: All lines but those matching are printed.
	- `-x`: (Exact) only lines matched in their entirety are printed
	- `-c`: Only a count of matching lines is printed.
	- `-n`: Each line is preceded by its relative line number in the file
	- `-l`: Instead of lines, the names of the files that match are printed 
		- i.e., . answers the question: “what files contain this pattern?”
	- `-i`: he case of letters is ignored in making comparisons - that is, upper and lower case are considered identical.
	- `-w`: Match a whole word (must have whitespace or newline both before and after the word)
	- `-E`: allows the use of extended regular expression
	- `-r/-R`: cause `grep` to recursively search subdirection

### `sed`
- Non-interactive string editing tool
- Available for file and standard input
	- `sed <command>`: Standard input
	- `sed <command> <file>`: operate on file

- `s/<pattern>/<replacement>/`
	- Substitute pattern
	- Operates only for first occurrence
	- `s/<pattern>/<replacement>/g` for global option
	- `whitespace` is permitted


Machine Information
- `hostname`: Prints out the name of the machine
	- Helpful is you have some terminals running `shh` sessions connected to various servers
- `uname`: Prints out information about the operating system

## Editing Files(vim)

`vim` has multiple modes
- `Normal mode`: For commands
- `Insert mode`: For actually typing text into file
- `Visual mode`: For copying and pasting

[Additional Source]([마우스 없이 코딩한다구요? | 얄코 (yalco.kr)](https://www.yalco.kr/10_vim/))

- `vim <filename>`: Open the file, or create if there is no file by that name exist
- `:w`: Write (save) the file
- `:q`: Quit (not allowed if there is unsaved work) 
- `:q!`: Quit without saving 
- `:wq`: Save and quit 
- `i`: Switch to insert mode
- `esc`: Get to normal mode by insert mode
