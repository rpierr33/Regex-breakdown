# Title (Regex Breakdown / Tutorial )

## Introductory paragraph 

(Regular expressions, better known as REGEX, can be defined or explained as a *sequence of characters with the ability to search through text or strings, and validate it against set, defined conditions or rules.*  REGEX can be used to do data validation, web scraping, or advanced find and replace operation, like changing certain characters or get only email addresses from a document.)

## Summary

We are using a regular expression that will ensure the input matches an email address. 
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

lets break down this expression to get a better understand of what each character is doing here. 


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

Here are some common use cases for REGEX, Regular Expressions.\
1. verify the structure of strings
2. extract substrings form structured strings
3. search / replace / rearrange parts of the string
4. split a string into tokens


### Anchors
an Anchor example is provided as the very first character in the example prodided above, ^. This anchor character lets the computer knows that a match has to occur at the very start of the string.  To put simply, if even one character did not match the terms of the regex when looking at a string, that string would then be invalid.  In an example of the email, without the ^, an email address with brackets in front of it would be considered as a valid email.  However, since the ^ is present, the bracket would have to be removed or the email would be considered as being invalid.\

example - \
email@email.com -- invalid          [email@email.com -- valid\


### Quantifiers

Quantifiers can be seen as a way to limit the string or a section of the string. In the example provided above, we have a couple of quantifer examples, {2,6} and +. The {2,6} requires that this part of the string must be between 2 and 6 characters long. the + operator added at the end of the subexpressions, which means, that the created regex matches a specific pattern one or more times. To put plainly, anything before the @ of an email has to be one or more characters long to create a match. 

### OR Operator
The OR Operator, also known as the pipe character | is used as the selection operator.  This operator matches alternatives. For example, if a pattern is supposed to match strings 1 and 2, the following pattern will do the trick:  \

1|2


### Character Classes
Character classes are used to define a set of allowed characters.  the set of allow characaters is put in square brackets, and each of the allowed characters is listed. for example, [abcdef] = [a|b|c|e|f]. the pattern [ab] [cd] matches [ac], [ad], [bc], [bd]\
but it does not match [ab] or [cd].

an example of character classes in the exmaple provided above, is \d. Which matches a single character that is a digit from 0-9, so it'll match 9 but but not 99.


### Flags

Flags are optional parameters that can be added to a plain expression and make it search in a different way. for example, the flag i (Ignore Casing), makes the expression search case-insensitively. The flag s (Dot All), makes the wild character . match newlines as well. The falg m (Multiline) makes the boundary characters ^ and $ match the beginning and ending of every single line instead of the beginning and ending of the whole string.

### Grouping and Capturing
Capturing groups means that users are able to group sub-patterns in sections using round brackets. In the regex provided above to match emails, we used this method to construct different sections of our regex, known as subexpressions. ([a-z0-9_\.-]+), ([\da-z\.-]+), and ([a-z\.]{2,6})
as you can see, the subexpressions are enclosed in parentheses or rounded brackets.

### Bracket Expressions
Bracket expressions, also known as positive character groups are a list of characters and/or character classes enclosed in brackets []. similarly to character classes, these bracket expressions can be used to match single characters in a list, or a range of characters in a list. If the first character of the list is the carat ^ then it matches characters that are not in the list.
in our example, [a-z0-9_\.-], this is our first bracket expression. This is defining a range of characters from "a" through to "z". So, we are claiming that the entire alphabet is valid.

### Greedy and Lazy Match
Greedy matches the string plus an excess of information, whereas lazy matches will be shorten. Our example did include greesy matches in the form of the + quantifier, and the {2,6}. the + quantifier will match as many times as possible and the {} will match the last capture group.

### Boundaries
tu put it plainly, the word boundary \b allows users to carry the hwole word using a regular expression. 

For example, the code below will return "JS"

```

console.log('Hello, JS!'.match(/\bJS\b/)); 

```

The three positions that qualify as word boundaries are as follows:

1. If the first character in a string is a word character, it comes before the first character in the string.
2. If the last character in a string is a word character, it comes after it.
3. If one of the characters in a string is a word character and the other is not, there is a space between them.


### Back-references

Backreferences match the same text that a capturing group previously matched. Let's say you want to match the opening and closing HTML tags, as well as the text between them. We can reuse the name of the tag for the closing tag by putting the opening tag into a backreference.

### Look-ahead and Look-behind

Lookahead and lookbehind, also known as "lookaround," are zero-length assertions similar to the start and end of line, as well as the start, ^, and end of word anchors, $, discussed earlier in this breakdown. Lookaround differs in that it matches characters before giving up the match and returning only the result:

## Author

My name is Ralph Pierre. I'm a full stack web developer from South Florida. If you'd like to see my best and latest work, here's a link to my protfolio: https://rpierr33.github.io/portfolio/


or, check out my github: https://github.com/rpierr33
