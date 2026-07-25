# Text Processing in linux using system utilities

## awk



## cut

Remove sections from each line of a file.

cut -d <delimiter> -f 1 /path/file
Returns the first field that is separeted by the delimiter

cut -c 7-11,14 file.md
Returns the chars in position 7 to 11 and 14

## grep

## sed

String editor. 

sed 's/foo/bar' < file.txt
Seach for first occurrence of sequence foo and replaces it with sequence bar

sed 

## tr

Translate or delete characteres

tr <set-to-replace> <set-to-replace-with> < file.txt
Ex: tr [a-z] [A-Z] < file.txt

tr -d <pattern> < file.txt
Removes the a class of chars

tr -s <char> < file.txt
removes repetead char or specified pattern and replaces it with a single ocorrence of the char.
