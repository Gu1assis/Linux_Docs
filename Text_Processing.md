# Text Processing in linux using system utilities

## Regex cheat sheet

^ -> start of the line
$ -> end of the line
. -> any char

## cut

Remove sections from each line of a file.

cut -d <delimiter> -f 1 /path/file
Returns the first field that is separeted by the delimiter

cut -c 7-11,14 file.md
Returns the chars in position 7 to 11 and 14

## grep

Seach patterns on file's contents

grep <pattern> file1 file2 ...

Some useful flags:

-A<number>, -B<number> or -C<number>: get the n lines after, before or around.

-i : ignore case sentivity.

-o: print only the pattern, not the entire line.

-c: outputs the count of matching lines for each file.

-l: outputs the names of the files that contains a match.

-n: prints the number of the line.

-r: read all files under each directory

If the file path passed is a directory, you can use -d skip to ignore it or -d recurse to read files inside of it. It is the same thing as using the -r flag.

## wc


## history

returns used commands.

You can use !id to execute the command again.

Of course you can search:

history | awk '$2 == "something" { print $0 }'

or simply 

history | awk '$2 == "something"'

If you dont want the command to end up in the history, type a spece before it.
## sed

String editor. 

sed 's/foo/bar' < file.txt
Seach for first occurrence of sequence foo and replaces it with sequence bar

sed -i 's/foo/bar/g' file.txt
Search and replaces every occurences and write to the file

sed 'foo/s/bar/baz' < file.txt
From lines with sequence foo, replace bar with baz

You can use -e to pass on multiple expressions:
cat /etc/passwd | sed -e 's/root/bunny/g' -e 's/no..dy/somebody/g'

## tr

Translate or delete characteres

tr <set-to-replace> <set-to-replace-with> < file.txt
Ex: tr [a-z] [A-Z] < file.txt

tr -d <pattern> < file.txt
Removes the a class of chars

tr -s <char> < file.txt
removes repetead char or specified pattern and replaces it with a single ocorrence of the char.
