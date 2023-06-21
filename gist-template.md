# Regex Help Gist

## Summary

I will be breaking down a regular expression, aka "regex", sequence into it's most basic forms to help those who are looking to understand regex better by listing some common rules and lingo.

This is our example expression, which is used for matching a HTTPS Url:

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

Information that I am attempting to point out inside our example regex will be wrapped inside a double asterix `(**(information)**)`.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

Regex is known as a literal, so it has to be wrapped in Slash characters (/), then followed by (^) to signify the start of the string, then ($) is applied at the end to signify the end of the string.

Inside our example:

`**/^**(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?**$/**`

### Quantifiers

Quantifiers is what allows us to specify how many characters are allowed inside a specific field.

`/^(https?:\/\/)**?**([\da-z\.-]+)\.([a-z\.]**{2,6}**)([\/\w \.-]***)***\/**?**$/`

`{2,6}` meaning it allows 2 to 6 characters inside this portion of the HTTPS Url.

Some common quantifier and quantifier rules include: (below examples are provided by https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial)

`*` Matches the pattern zero or more times.

`+` Matches the pattern one or more times.

`?` Matches the pattern zero or one time.

`{}` Curly brackets can provide three different ways to set limits for a match:

`{ n }` Matches the pattern exactly n number of times.

`{ n, }` Matches the pattern at least n number of times.

`{ n, x }` Matches the pattern from a minimum of n number of times to a maximum of x number of times.

Each of these quantifiers can be made lazy by adding the `?` symbol after it, meaning it will match as few occurrences as possible.

### Grouping Constructs

Regex is more or less a simple set of rules, and if all the rules are matched, then the regex expression is correct. Sometimes you need to group your rules inside an epxression so they don't interfere with other rules.
The primary way to do this is by using Parenthesis: `()`.

`/^**(https?:\/\/)**?**([\da-z\.-]+)**\.**([a-z\.]{2,6})****([\/\w \.-]*)***\/?$/`

More than one set of parenthesis' inside an expression are known as subgroups.

### Bracket Expressions

This is the core of a regex expression when you want to be as specific as possible with what can be matched for that part of your regex.

`[a-z]` means everything from "a" through "z" in the alphabet.

`[0-9]` means everything from "1" through "9" numerically.

`[_-]` means underscore and dashes are allowed.

In our example:

`/^(https?:\/\/)?(**[\da-z\.-]**+)\.(**[a-z\.]**{2,6})(**[\/\w \.-]***)*\/?$/`

### Character Classes

Character Classes inside a regex expression dictate a range of characters more easily than if we did it manually inside our expression.

Some common character classes include:

`.` matches any character except the new line character `\n`.

`\d` matches any Arabic numeral digit. This class is equivalent to the bracket expression `[0-9]`.

`\w` matches any number or letter from the latin alphanumeric alphabet, including underscore (`_`).

`\s` matches a single whitespace character, including tabs and line-breaks.

In our example:

`/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

### Flags

Flags go at the end of a regex string, after the second slash, to signify additional functionality or limits of the expression. Here are three common ones:

`g` tests against all possible matches in the string provided.

`i` means the expression will ignore cases and capitals.

`m` treats the string as if it were multiple lines.

We have no flags inside our example.

### Character Escapes

Also known as the backslash `\`.

Character escapes is when you want to use a character to define a regex rule without allowing the expression to read it as a defining part of the rule. IE if you wanted to use `[` as a part of a search rule without accidentally starting a bracket expression, then you would attach a backslash to the front of it like this: `\[`.

Inside our example:

`/^(https?:**\**/**\**/)?([\da-z**\**.-]+)\.([a-z**\**.]{2,6})([**\**/\w**\**.-]*)***\**/?$/`

## Author

My name is Noah Ralph; I am a full-time lifeguard, swim instructor, and lifeguard instructor, and I am currently becoming certified in full-stack web development through the University of Oregon.
