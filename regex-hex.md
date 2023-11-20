# Regex Tutorial: Matching a Hex Value

Validating colors can be tricky in JavaScript. Does the user enter a written color like 'red' or 'blue'? What happens if the users spell it wrong? Good news is that all colors can be written in hexidecimal form, like `#ffffff` or `#fff` which represents the color, `white`. This tutorial describes a regular expression (i.e., REGEX) for validating a color hex value to make sure it is of proper length and form to prevent errors within your code.

## Summary

The following code snippet is a common regex for matching a color hex value. This tutorial breaks down the regex and explains each of its components. 

```
/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
```

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [The OR Operator](#the-or-operator)
- [Bracket Expressions](#bracket-expressions)

## Regex Components

### Anchors
The characters `^` and `$` are the anchor components. They start and end the regex expression.
* `^` : represents the start of the regex. The following expression is used to look for either an exact match or range of possible matches.
* `$` : represents the end of the regex. The preceding expression is used to look for either an exact match or range of possible matches.
* `#?([a-f0-9]{6}|[a-f0-9]{3})` : is the expression to match for this regex because it is between the anchors


### The Hexidecimal Hash Exact Match
A hexidecimal string always starts with hash character, `#`, and this is an exact match character type. If the string does not start with a `#`, it will fail to be a match. 
* `#` : represents the start of the a standard hex value and is an exact match type. 
* Examples: 
  * Successful match: `#aaa`
  * Not a match: `aaa`

### Quantifiers
We only need one string for a hexidecimal value. Since this regex includes the option to match a string of length `{6}` OR `{3}` characters, we use the quanitifier `?` to return only the first match or none at all.

* `?` : represents matching the pattern zero or one time, as many times as possible within a large string.
* `{6}` : represents matching the pattern exactly `6` times. So the matching string will be of length, `6`.
* `{3}` : represents matching the pattern exactly `3` times. So the matching string will be of length, `3`.

* For an example, say we enter the string `#123456`.  This regex will return `#123456` and `#123` as possible matches. With the `?`, the regex will only return the first match, `#123456`.


### Grouping Constructs
The `([a-f0-9]{6}|[a-f0-9]{3})` is a capturing group, denoted by the `()`, and will return any matched character sequences. 
* `()` : represents a capturing group, meaning the capturing group will capture the matched character sequences.
* For an example, say we enter the string `#123456`.  This regex will return `#123456` and `#123` as possible matches.


### The OR Operator
In the regex expression, `([a-f0-9]{6}|[a-f0-9]{3})`, the `[a-f0-9]{6}` and `[a-f0-9]{3}` are alternative capturing groups, denoted by the `|`, and will return either matched character sequences. Since we are using the `?` quantifier, the regex gives preference to the first alternative.
* `|` : represents alternative capturing groups, meaning the capturing group could be either subexpression to return the matched character sequences. Since we are using the `?` quantifier, the regex gives preference to the 1st alternative.
* `[a-f0-9]{6}`: is the first alternative and represents matching the bracket expression exactly `6` times. So the matching string will be of length, `6`.
* `[a-f0-9]{3}`: is the second alternative and represents matching the bracket expression exactly `3` times. So the matching string will be of length, `3`.
* For an example, say we enter the string `#123456`.  This regex will return `#123456` and `#123` as possible matches. With the `?`, the regex will only return the first match, `#123456`.


### Bracket Expressions
The bracket expressions, `[a-f0-9]`, matches a single character from two lists of characters, `a-f` or `0-9`. A hexidecimal value is 0 to 15 in decimal representation. Hexidecimal uses digits `0` to `9` as normal, and uses `a` to `f` to represent `10` to `15`, respectively. This reqex is case sestivitve, only lower case characters are matches.
* `a-f` : represents matching a character from `a` to `f`. This reqex is case sestivitve, only lower case characters are matches.
* `0-9` : represents matching a character from `0` to `9`
* Examples: 
  * Successful matches: `0` or `a`
  * Not matches: `A` or `z`


## Author

* GitHub profile: [nestibry](https://github.com/nestibry)
* Naturally inquisitive, 'Bryan with a Y' is the perfect moniker for me. Key Points: First and foremost, I'm a devoted father and husband. Being an avid outdoor enthusiast, I derive immense joy from hiking and mountain biking. I possess extensive expertise as a Software Engineer and Machine Vision Engineer, with a foundation in Electrical Engineering and a background in teaching Mathematics at the secondary level. [Contact me on LinkedIn](https://www.linkedin.com/in/bryan-nestingen/) to learn more about my eclectic background!