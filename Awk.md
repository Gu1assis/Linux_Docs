# awk

Awk is a text processing language.
It works with a sequence of 'pattern {action}' pairs.

If a action is ommited, it is implicitly { print }.

## Introduction

You can pass an argument to apply on every line of the file.

awk '{ print $0 }'

$0 -> entire line
$n -> the nth field, delimiters are spaces. You can use -F<delimiter> to pass a new delimiter.

You can use a printf sintax:

cat /etc/passwd | awk -F: '{ printf("%s has shell %s\n", $1, $7) }'

And add conditionals:

cat /etc/passwd | awk -F: '$1 == "root" { printf("%s has shell %s\n", $1, $7) }'

## Common Operations

print -> prints argument.

BEGIN { FS=":"; OFS="-" } -> use : as file separator and outputs it as -.

length() -> calculates length of the argument



## Common flags

-F <delimiter> -> changes the delimiter


