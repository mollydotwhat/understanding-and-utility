# Some Notes on Regular Expressions

## Summary
The regular expression `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` evaluates whether a string is a valid email address. This otherwise meaningless collection of characters defines very specific rules it should match. The following is an attempt to explain how they fit together to do that.

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
Anchors define where you look for the parameters being set. `^` goes before the rules to match, and `$` is telling you the rules are before it.
So `^([a-z0-9_\.-]+)` means everything following it (in those parentheses), is telling you what the rules are for the first part of the string.


### Quantifiers
Putting a `+` at the end of some parameters tells the expression to look for as many matches for those rules as possible/available. So, *every* time it finds something that meets those parameters, it counts as matching.

### Grouping Constructs
Sometimes (often) a regex will be more complicated, including rules to evaluate for different parts/sections of a string. In that case, you can put those within parentheses. So, for example, the section `^([a-z0-9_\.-]+)@` checks that the string meets the parameters before the `@` character, and the group `([\da-z\.-]+)` is defining the requirements for a part of the string which comes after it. Those are called subsections.

By using the `:` character, you tell the regex to match conditions in parentheses in that order specifically. So `([0-9]):([a-z])` would mean the numbers have to come BEFORE the letters.

### Bracket Expressions
Brackets define for a range of characters to match. For example, `[a-z0-9_\.-]` includes every letter including and between a and z, every number including and between 0 and 9, and the characters `_`, `.`, and `-`.  A `^` placed *inside* brackets means *exclude* the characters inside it.

### Character Classes
`.` by itself matches any character except for a line break (`\n`). You can shorten the expression `[0-9]` by putting `\d`. You can include those characters AND all alpha characters, AND the `_` by using the character class `\w`. You can use that instead of typing `[A-Za-z0-9_]`. The above expression (email validation) uses `\d` in one instance. 


### The OR Operator
The pipe (`|`) is the or operator. For example, the expression `(f|y|i)` would mean to look for one of those three letters.

### Flags
Flags are the only things that go *outside* a regex's slash characters (`/`expression here`/`). The email validating expression doesn't use any, but the three most common are `g`--global, meaning it should test for all possible matches, `i` means that capitalization isn't taken into account, and `m` flags a multi-line input (treat input on multiple lines as multiple lines).

### Character Escapes
`\` is a character escape. It means that the character immediately following it should be interpreted by the expression as a literal string, instead of an operation it might mean somewhere else. The chosen expression uses a character escape to make `.` just the literal character, in several groupings.

## Author
...is studying Javascript, a process which includes learning about regular expressions. She's aware that this is a short overview, and not a comprehensive breakdown of the uses and meaning of all regular expressions. 
