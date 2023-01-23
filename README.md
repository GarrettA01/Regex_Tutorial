# REGEX Tutorial

## Summary

This README file goes over the basics of REGEX aka Regular Expressions, goes over what ach type is, how its used, and the syntax to write it.

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

Anchors have special meaning in regular expressions. They do not match any character. Instead, they match a position before or after characters:

- `^` – The caret anchor matches the beginning of the text.
- `$` – The dollar anchor matches the end of the text.

### Quantifiers

- The quantities `n` and `m` are integer constants.
- Ordinarily, quantifiers are greedy.
- They cause the regular expression engine to match as many occurrences of particular patterns as possible.
- Appending the `?` character to a quantifier makes it lazy.
- It causes the regular expression engine to match as few occurrences as possible.

### Grouping Constructs

Grouping constructs delineate the subexpressions of a regular expression and capture the substrings of an input string. You can use grouping constructs to do the following:

- Match a subexpression that is repeated in the input string.
- Apply a quantifier to a subexpression that has multiple regular expression language elements.
- Include a subexpression in the string that is returned by the Regex.Replace and Match.Result methods.
- Retrieve individual subexpressions from the Match.Groups property and process them separately from the matched text as a whole.

### Bracket Expressions

- `[]`

- Brackets indicate a set of characters to match. Any individual character between the brackets will match, and you can also use a hyphen to define a set.

`'elephant'.match(/[abcd]/) // -> matches 'a'`

- `{}`

- Curly braces are used to specify an exact amount of things to match. They are used after an expression: \na{2}\ will only match 'na' exactly twice.

`'panama'.match(/na{2}/) // -> no match`
`'banana'.match(/na{2}/) // -> matches 'nana'`

- `()`

- Parentheses represent remembered matches. This is especially useful for find-and-replace operations or any time you need to do something with part of the match. When a match is remembered you can use $n to refer to it, starting with $1 up to $9, or with $& to refer to the entire match.

### Character Classes

- With a “character class”, also called “character set”, you can tell the regex engine to match only one out of several characters. Simply place the characters you want to match between square brackets. If you want to match an a or an e, use `[ae]`. You could use this in `gr[ae]y` to match either gray or grey. Very useful if you do not know whether the document you are searching through is written in American or British English.

- A character class matches only a single character. `gr[ae]y` does not match `graay`, `graey` or any such thing. The order of the characters inside a character class does not matter. The results are identical.

### The OR Operator

- `|`

- Grouping and alternation are core features of every modern regular expression library. You can provide as many terms as desired, as long as they are separated with the pipe character: `|`. This character separates terms contained within each (...) group. Take the following example, for instance:

- `^I like (dogs|penguins), but not (lions|tigers).$`
- This expression will match any of the following strings:

- `I like dogs, but not lions.`
- `I like dogs, but not tigers.`
- `I like penguins, but not lions.`
- `I like penguins, but not tigers.`

### Flags

- Regular expressions have optional flags that allow for functionality like global searching and case-insensitive searching. These flags can be used separately or together in any order, and are included as part of the regular expression.

- `d` Generate indices for substring matches.
- `g` Global search.
- `i` Case-insensitive search.
- `m` Allows `^` and `$` to match newline characters.
- `s` Allows `.` to match newline characters.
- `u` "Unicode"; treat a pattern as a sequence of Unicode code points.
- `y` Perform a "sticky" search that matches starting at the current position in the target string.

### Character Escapes

- The backslash in a regular expression precedes a literal character. You also escape certain letters that represent common character classes, such as `\w` for a word character or `\s` for a space. The following example matches word characters (alphanumeric and underscores) and spaces.

- "Are you there, Alice?, asked Jerry.", // source
  "(here|there).+(\w+).+(said|asked)(\s)(\w+)\." ); // regular expression
  "there, Alice?, asked Jerry."

- `(here|there).+`

- Matches “there”, a comma, and a space.

- `(\w+)`

- Matches “Alice”.

- `.+`

- Matches “?, “.

- `(said|asked)(\s)`

- Matches “asked” followed by a space. Without the space, the match would end here; “asked” is followed by a space in the source string.

- `(\w+)\.`

- Matches “Jerry” and a period.

## Author

This README was constructed for personal use by Garrett.

[Github](https://github.com/GarrettA01)

[Email](gman.anderson2001@gmail.com)
