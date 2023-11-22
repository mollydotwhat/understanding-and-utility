THIS IS STILL A DRAFT.

# Title
is intro necessary?
(email)
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` 
<!--or hexcode: `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`, depending on which one I can explain most clearly... -->

## Summary
what it says on the tin
JUST SAY WHAT THIS SPECIFIC ONE DOES OVERALL. You don't have to sell someone on regex usefulness.

## Table of Contents
how long is this going to be??
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

characters that are anchors: '&', '^'. (the ones inside the quotes)
`^` goes before exact string to match, or if you put them in brackets you can have a list of matches.
first anchor `^([a-z0-9_\.-]+)` where ^ means that from a to z, 0 to 9, or underscore matches. The use of characters `()`, `+`, `\.-` will be explained in later sections. 

'$' means match the string in FRONT of the anchor. Works with brackets the same as above.


### Quantifiers
limiting, but also greedy/lazy
+ at end means as many as possible/available
in `^([a-z0-9_\.-]+)` the `+` asks it to match *every* time one of the characters inside the `[]` is present. So `th32i_ng7` would match.

### Grouping Constructs
`()` capturing group

### Bracket Expressions
Brackets are for a range of characters to match. For example, `[a-z0-9_\.-]` will match all of these: `56ink`, `shar1e`, `heat-wave`, and `teapot`.
carat *inside* brackets means *exclude* those characters.

### Character Classes

### The OR Operator

### Flags

### Character Escapes


## Author
about me (SHORT i hope. how do you write these without sounding either arrogant or miserable???), link to github profile