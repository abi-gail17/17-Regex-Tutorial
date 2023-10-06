# The Hex Value Regex Tutorial

A regex (regular expression) is a sequence of characters match a pattern in text i.s the string of characters follow a set of criteria or rules given by the regex. They are often used to locate strings of characters, replace them,  or validate them in a document or place where characters are input. 

## Summary

In this tutorial, we will be exploring and explaining the regex used to match HEX values:

`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

Below, we will be going over the datails of its anchors, quantifiers, grouping constructs, bracket expressions, character classes, OR operator, flags, and character excapes.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

The HEX code regex: `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

### Anchors

The anchors of a regex signify the beginnning and end of the string. In the HEX regex, `^` is used to show the beginning of the string and `$` is to show its end. These are not actual characters in the string but just show what the string must begin and end with. So, in this specific regex, the `^#?` shows that the # at the beginning is optional with the # followed by ?. The optional # must then end with something that follows this pattern: `[a-f0-9]`. You may notice that `{6}` and  `{3}` are not included, and that is because they are [Quantifiers](#quantifiers).

### Quantifiers

The quantifiers in this regex are denoted by numbers wrapped in `{}`. They set the limits of the string your regex matches. In the HEX code regex, the quantifiers are `{6}`and `{3}`, but not `{3, 6}`. In a regex, quantifiers can come in a few forms: `{x}` where the pattern matches exactly x number of times, `{x ,}` where the pattern matches at least x number of times, and `{x, y}` where the pattern matches from a minimun of x times to a maximum of x times. However, you may otice that in this regex, there two quantifiers separated by `|`, which is an [OR operator](#the-or-operator).

### Grouping Constructs

The grouping construct `()` groups the regex between them.Anything within them is treated as a singular unit. In the HEX code regex, the grouping construct is `([a-f0-9]{6}|[a-f0-9]{3})`.

### Bracket Expressions

Anything in a set of square brackets `[]` is known as a bracket expression. The bracket expression represents the range of characters we want to match. Because they outline the characters we want to include, bracket expressions are also known as a positive character group.

In this regex, the bracket expression is `[a-f0-9]`, which appears twice because of the [OR Operator](#the-or-operator).

"a-f" means that any lowercase letter between a and f can be in the string.

"0-9" means that any number from 0 to 9 can appear in the string.

### Character Classes

Character classes in a regex defines a set of characters that can occur in an input string to match. `.` matches any character except fot the one denoting a new line `\n`. `\d`is any Arabic digit and means the smae thing as the [bracket expression](#bracket-expressions) [0-9]. There are other character classes, but none apply in the HEX regex except for `\d`. Please note that character classes are case sensitive and therefore `\d` and `\D` are not the same as the uppercase D matches non-digit characters.

### The OR Operator

The OR operator `|` basically groups two bracket expressions and says that the regex can follow one expression or the other. For example, `([a-z]|[0-9])` shows that a string can be a string consisting of lowercase letters from a-z or numbers from 0-9, but not both. So the string can be asdf or 1234 but not hell0.

In the HEX regex, there is an OR operator that seperates the [bracket expressions](#bracket-expressions) `[a-f0-9]{6}` and `[a-f0-9]{3}`, meaning that the HEX code string can consist of lowercase letters from a to f and numbers from 0 to 9, but can only be *6* characters long **OR** *3*, not 3 to 6 characters. So, with this knowledge, 222 or a1f45d can are permissible, but not fde1 or 12e4c becasue they are not 3 or  characters long.

### Flags

Although regexs have to be wrapped in slash characters, the one exception to this rule are flags. Flags define additional functionality to the regex and ae placed at the very end outside the `/`. There are 6 optional flags: 

`i`: means case-insensitive which means that the pattern will match no matter whether you use UPPERCASE or lowercase.

`g`: means global. That means the regex will find all the strings that match its pattern instead of stopping at one.

`m`: means multi-line matching. Means that the inout string should be treated as multiple lines

`s`: dot-all. Means that `.` can matche any character, including newline characters.

`u`: unicode matching means that it interprets the pattern and input string as unicode.

`y`: sticky. The regex only tries to match the string from index indicated by lastIndex property.

There a no flags at the end of the HEX code regex but you can add any of these if you wish for your own purposes.

### Character Escapes

Character escapes `\` allows characters that would otherwise serve a function in a regex such as {}, [], /, and - to be interpreted literally. For example, `\[` would allow the regex to look for the square bracket as a character instead of seeing it as something to encapsulate a [bracket expression](#bracket-expressions).

There are no character eacapes in the HEX code regex.

## Author

I'm Abigail, a developer always looking to improve. You can contact me at my [Github](https://github.com/abi-gail17).

##Sources
[The Full-Stack Blog Regular Expression Tutorial](https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial)
