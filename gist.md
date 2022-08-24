# Charles_Morton_Regex_Tutorial

Regular Expressions (regex) are an extremely valuable tool, especially when it comes to user input. Users can be unpredictable, so when we need a string formatted in a certain way, we use regular expressions. They are also used to search through strings and find substrings that abide by certain specifications.

## Summary

This document is a brief summary and explanation of various regex components. Examples are Included.

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

### Anchors

Regex anchors are used create rules that specify where the substring in question is occuring. 
<br>
The carat anchor `^` is used to specify that the substring must be at the beginning of a string. `/^A/` would match a string such as "Apple", but not "apple" or "BATCH".
<br>
The `$` anchor is used to match to the end of an input. `/t$/` would match an input "last" but not "lasted".

### Quantifiers

Quantifiers specify the number of times a specificed character may appear in a given string.
<br>
The `*` quantifier specifies that a character may appear 0 or more times. `/bo*/` would match a string "booooo" or "b", but not "oooo".
<br>
The `+` quantifier specifies that a character must appear 1 or more times for the string to match. `/bo+/` would match the string "bo" or "booooo", but not "b" or "ooo".

### Grouping Constructs

Grouping constructs are used to return the values of the matching substrings in the input.
<br>
`/?(square)\w\d/` would result in all substrings matching the format "a1" or "b5" to be returned under the property of `matches.groups.square`

### Bracket Expressions

bracket expressions match any character within the brackets
<br>
`/[a-z]/` would match to anything containing only the characters a-z and exclude anything containing numbers, special characters, or capital letters.
<br>
`/[a-z0-9/` would match to anything alphanumeric.
<br>
`/[a-df-z]/` would exclude anything containing the letter "e".

### Character Classes

Character classes are a combination of [Bracket Expressions](#bracket-expressions) and [Character Escapes](#character-escapes) used to denote the difference between character types.

### The OR Operator

The OR operator `(x|y)` allows for partial condition matching inside the regular expression.
<br>
Where the expression `/ab/` would have to match the string "ab" exactly, `/(a|b)/` allows the string to match "a" or "b", but not "ab".

### Flags

Flags allow for more advanced searches.
<br>
The `i` flag allows the search to be case insensitive. Flags are added to the end of the regular expression, after the final `/`.
<br>
`/[a-z]/i` would match any string that contains the values A-Z both lowercase and capitalized. Without the `i` flag, that expression would only return instances that are all lowercase.

### Character Escapes

Character escapes will match to their character type.
<br>
`/\w/` will match to any word character. it is essentially shorthand for `/[A-Za-z0-9_]/`.
<br>
`/\d/` will match to any numeric character.
<br>
Capitalizing the specification will add a bang operator to the type specified. For example, `/\D/` will exclude any digits.

## Author

My name is Charles Morton. I am a student through the Georgia Tech Coding Bootcamp. I am based out of Charlotte, North Carolina.

My [Github](https://github.com/Alkarias).
