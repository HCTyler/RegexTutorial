# Regex Tutorial

In this tutorial, I will be taking a brief look into what Regex, short for regular expression, are and how they work. And just like with any language, they can be broken down into its most simple parts and can easily understood.

## Summary

Regex is a string of text taht allows you to create patterns that match, manage, and locate text. An example is:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

This expression is used to verify a valid email address.

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

Achors are the characters within the regular expression that allows the user to match strings that begins or ends with certain characters.

An example of anchors are:

`^`

    This anchor matches the beginning of a text.
`$`

    This matches the ending of a text.

`m`

    This is an inline modifier that enables the use of `^` and `$` to watch the beginning and the end of a string.

The carrot top anchor `^` and the dollar sign anchor `$` can both be seen in the example above.

/`^`([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})`$`/


### Quantifiers

Quantifiers specifies how many instances of a character, group, or character class that requires to be present that the regex matches. This means that quantifiers allows characters, metacharacters, and entire subexpressions to be repeated.
By default, quantifiers are greedy, meaning they will match as many occurances of a pattern as possible. Adding a `?` to a quantifier makes it lazy, meaning it will match as few offurrences as possible. Adding  the quantifier in `{`n`}` will match the quantifier an n number of times.

The example above:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]`{2,6}`)$/

`{2,6}` is the quantifier that matches the preceeding token 2 to 6 times.

### Grouping Constructs

Grouping constructs delineate the subexpressions of a regular expression and captures the substrings of an input string. This means that anything within a `(``)` is taken as a a subexpression.

In the example above, there are three groups

/^`([a-z0-9_\.-]+)`@`([\da-z\.-]+)`\.`([a-z\.]{2,6})`$/

Which can be seen like (1)@(2).(3)
a template for an email address.

### Bracket Expressions
Braket expressions are used to indicate sets of characters, that can be used to match and search for specific characters or strings. This can be done by enclosing the characters or string between `[` `]`.

In the example above, 

/^(`[a-z0-9_\.-]`+)@(`[\da-z\.-]`+)\.(`[a-z\.]`{2,6})$/

there are three bracket expressions:

`[a-z]` - indicates a string using lowercase letters between a-z. To include uppercase letters, the uppdercased character needs to be included in the bracket expression. `[a-zA-Z]`

`[0-9]` -this part of the bracket indicates matching a numeric character ranging from 0-9.

`[_/.-]` -this part of the bracket matches particular symbols and punctutation. This is case, it is the underscore, slash, period or hyphen.

### Character Classes

Character classes or character sets is a special notation that allows to match any symbols or characters from a set.

Some examples of character classes are:

`.`

    This matches any single character except line terminators. If the dot is inside a character calss, it loses its special meaning and matches the dot symbol itself.

`\d`

    This matches any numeric characters. It is similar the bracket expression [0-9]

`\w`

    This matches any alphanumeric character including the underscore. This is similar to the bracket expression [A-Za-z0-9_]

`\s`

    This matches a single white space character, including space, tab, form feed and other unicode spaces.

`\D \W \S`

    Capitalizing the letters performs the inverse function of it's fiven lowercase counterpart. For example, \D matches non numeric characters.

### The OR Operator

The OR operator is a logical feature that allows matching an expression or character from either side of the `|` operator.

For example: I like `(cats|dogs)` will result in matching "I like cats" or "I like dogs".

### Flags

Flags, in a regular expression, are optional parameters that modifys its behavior for searching. It is denoted using a single lowercase alphabetic character and are implemented after using the forward slashe `/` for example `/hello/i`.

Some examples of flags are:

`i` - Ingore Csing makes the expression search case-insensitive.

`g` - Global makes the expression seach for all occurrences.

`m`- Multiline makes the boundary characters `^` and `$` match the beggining and ending of every single line instaed of the beginning and ending of the whole string.


### Character Escapes

Character escape is a character donated by a backslah `\` that allows the regex to interpret a character differently.
For exmaple:

`{` are used to begin a quantifier, but ading a backslash followed up with a curly bracket `\{` allows the expression to match a bracket symbol instead.

## Author

Hello, I'm a web developer student through the UCSD Coding Bootcamp program. Follow me on my [Github](https://github.com/HCTyler) at https://github.com/HCTyler.
