# Regex Tutorial for Email Matching 

Regular expressions (often referred to as regex) are sequences of characters that define search patterns. These expressions can be used to find certain patterns of characters within a string or to find/replace character(s) within a string. Validating inputs is also a use for regex. 

## Summary

This tutorial will examine the regex shown below to match an email address. 

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

This tutorial will discuss and explain each component of this regex. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [References](#references)

## Regex Components
### Anchors
Regex expressions need a way of signifying the beggining and the end of the expression. In this case, the start of the string is indicated by: 
`^`

The end of our string is indicated by: 
`$`

An exception to the above is if there are square brackets around the circumflex accent (as shown below). If this is the case, then the meaning changes to "not". 
`[^]`

### Quantifiers
Quantifiers communicate to the regex engine that it must match the quantity of the character or expression to its left. Examples include:

`?, +, *, {n}, {n, }, {n,m}`

This particular regex has two quantifiers: + and {}. We may take the former as i+ and understand that it matches the preceding item i one or more times. The latter taken as i{n,m} means that it matches the preceding item i between n and m times where m must be greater than n and both n and m must be positive integers.

### Character Classes
Character Classes ensure that a given sequence of characters matches a larger set of characters. Our regex has `/d` which looks for any digit in the string and `.` wildcard that matches any character in the string. 

### Grouping and Capturing
Grouping expressions allows us to extract the characters of a given group for validation. We define text between paranthesis as a group. In this case we have three groups. The first, ([a-z0-9_\.-]+), the second ([\da-z\.-]+) and the third ([a-z\.]{2,6}).

With email matching, we have 3 capture groups which allows us to have separate string rules apply to each.  `([a-z0-9_\.-]+)` separated by special character `@` followed by the second capture group `([\da-z\.-]+)`, and the third capture group `([a-z\.]{2,6})`. 

### Bracket Expressions
Bracket expressions define characters that can be matched. In our example, we use
`[a-z0-9_\.-]` 
`[\da-z\.-]` 
`[a-z\.]`

The first, `[a-z0-9_\.-]`, means that all the characters between a through z will be matched, as well as numeric characters between 0-9.

The second, `[\da-z\.-]`, checks for characters a-z and also checks for `\d` which is matching for digital digit. 

The third, `[a-z\.]`, - means that any characters between a through z will be matched and in addition a dot will be matched.

### Greedy and Lazy Match
Greedy and lazy qualifiers allow you to find the "greedy" (longest) and "lazy" (shortest) match. Our example shows `+` as the greedy match since it ensures a search of as many matches as possible for decimal numbers, alphabateical characters, and hyphens. 

### References 
[Javascript.info](https://javascript.info/regular-expressions)<br />
[Regexr](https://regexr.com/)<br />
[Regular-Expression.info](https://www.regular-expressions.info/)<br />
[RegExLib.com](https://regexlib.com/CheatSheet.aspx)<br />

## Author
Roxanna Vaught-Mijares is a geologist and is currently training to work as a web developer. Check out her [GitHub Profile](https://github.com/roxyvaught) or her [Portfolio](https://roxyvaught.github.io/) for more information. 
