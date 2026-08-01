# Basic vim 

Tip: type vimtutor in the terminal to get all the basic vim commands
There are two chapters:

vimtutor -c <chapter-number> 

# Commands in normal mode

h,j,k,l -> move the cursos right, down, up or left

x -> deletes the char in the cursor's position

r<char> -> replaces the with <char> in the current cursos's position

<number>G -> go to line <number>

gg -> go to first line of the file

G -> go to last line of the file

Ctrl + g -> shows file name em line count.

dw -> delete current word, including space.

ce -> delete current word and enter insert mode, excluding space.

y$ -> copy from the cursor's current position to the end of the line.

f<char> -> go to first <char> in the line at the right of the cursor.

%  -> go to ],} or ).

:s/foo/bar/g -> replaces foo with bar globally.

:r !<command> -> write output of the command in the current cursor's position.

R -> enters replace mode. Its like insert mode, but every char replaces the current char.

:help <command> -> get help.
