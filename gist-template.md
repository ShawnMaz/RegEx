# RegEx Review

Regular Expressions or RegEx or RegExp help extract specific information from a given piece of text. It is used to locate or validate a string from a given text. Almost all programming languages support RegEx. This document is meant to be a quick cheatsheet of some of the most used Regular Expressions.

## Summary

In this section we are going to take a look at and example of how to validate an email address.

Matching an email address can be done like the following:

            /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

Here is an example of the email validator in use:
![Example uses of the email validator](./assets/images/regex-1.png)

Detailed explanation of the components used in the RegEx above and more are given below.

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

## Regex Components

### Anchors
Anchors in RegEx are not used to match any character. They are used to match **a position** before or after characters.

* ```^``` - The caret anchor matches the beginning of the text.
* ```$``` - The dollar anchor matches the end of the text.

Examples:

**```^Hi```** - matches any string that **starts with Hi**.
![image showing the regular expression caret anchor](./assets/images/anchor1.png)

**```Shawn$```** - matches a string that **ends with Shawn**
![image showing the RegEx dollar anchor](./assets/images/anchor-2.png)

**```^Willy Wonka$```** - **exact string match** (starts and ends with Willy wonka)
![image showing the RegEx of both the caret and the dollar anchors](./assets/images/anchor-3.png)
**Exact string match** fails.
![image showing the regEx of both the caret and the dollar anchor failing](./assets/images/anchor-4.png)

**roar** - matches any string that has the text **roar** in it.
![image showing mach any text RegEx](./assets/images/anchor-5.png)

### Quantifiers
The purpose of the Quantifiers is to specify how many instances of a character or a group must be present in an input text for a match.

Examples:

**```xyz*```** - matches a string that has **xy followed by zero or more z**.
![image of quantifier that matches xy followed by zero or more c](./assets/images/quantifier-1.png)

**```xyz+```** - matches a string that has **xy followed by one or more z**.
![image of quantifier that matches xy followed by one or more c](./assets/images/quantifier-2.png)

**```xyz?```** - matches a string that has **xy followed by zero or one z**.
![image of quantifier that matches xy followed by zero or one z](./assets/images/quantifier-3.png)

**```xyz{2}```** - matches a string that has **xy followed by 2 z**.
![image of quantifier that matches a string that has xy followed by 2 z](./assets/images/quantifier-4.png)

**```xyz{2,}```** - matches a string that has **xy followed by 2 or more z**.
![image of quantifier that matches a string that has xy followed by 2 or more z](./assets/images/quantifier-5.png)

**```xyz{2,5}```** - matches a string that has **xy followed by 2 up to 5 z**.
![image of quantifier that matches a string that has xy followed by 2 up to 5 z](./assets/images/quantifier-6.png)

**```x(yz)*```** - matches a string that has **x followed by zero or more copies of the sequence yz**.
![image of quantifier that matches a string that has x followed by zero or more copies of the sequence yz](./assets/images/quantifier-7.png)

### OR Operator
The Or operator ```|``` or ```[]``` is used to pick from two choices.

Examples:

**```x(y|z)```** - matches a string that has **x followed by y or z**.
![image of the or operator that matches a string that has a x followed by y or z](./assets/images/or-1.png)

**```x[yz]```** - matches a string that has **x followed by y or z from the list**
![image of the or operator that matches a string that has a x followed by a y or z from the list](./assets/images/or-2.png)

### Character Classes
Character classes defines a set of character that when present in an input string results in a match.

**```\d```** - matches a **single character** that is a **digit**.
![image of the digit class](./assets/images/character%20class-1.png)

**```\w```** - matches a **word character** (alphanumeric character plus underscore).
![image of the word class](./assets/images/character%20class-2.png)

**```\s```** - matches a **whitespace character** (includes tabs)
![image of the whitespace class](./assets/images/character%20class-3.png)

**```.```** - matches **any character**. Use this class carefully. Often class or negated character class are faster and more precise.
![image of the any character class](./assets/images/character%20class-4.png)

```\d```, ```\w``` and ```\s``` have negated class which are ```\D```, ```\W``` and ```\S``` respectively.

### Flags
Flags are accessor properties that changes how a search is conducted on a given string.

* **```g```** (global) restarts the search from the end of the previous match instead of stopping after the frst match.
* **```m```** (multi-line) allows the ```^``` and the ```$``` anchors to use start and the end of a line, instead of the whole string.
* **```i```** (insensitive) makes the RegEx case insensitive.

### Grouping and Capturing
Grouping is a way of keeping a set of characters together.

Examples:

**```x(yz)```** - the paranthesis creates a **capturing group with the value of yz**. All the matching results are stored in an array and can be accesse using the index value.
![image of the grouped yz character](./assets/images/grouping-1.png)

**```x(?:yz)```** - creates a **non-capturing group**
![image of the non-captured group](./assets/images/grouping-2.png)

**```x(?<hi>yz)```** - creates a name for the captured group. It can later be accessed like a dictionary using the name.
![image of the named captured group](./assets/images/grouping-3.png)

### Bracket Expressions
Bracket expression lets you find a match by putting the conditions inside the brackets.

Examples:

**```[xyz]```** - matches a string that is **x or y or z**. It is the **same as a|b|c**. This expression can also be written as ```[x-z]```.
![image of the brackets expression xyz which is the same as the or notation](./assets/images/bracket-1.png)

**```[a-fA-F0-9]```** - case insensitive match for a **single hexadecimal digit**.
![image for finding the hexadecimal numbers using the brackets notation](./assets/images/bracket-2.png)

**```[0-9]%```** - matches a string of characters **from 0 to 9 before a % sign**
![image of the bracket expression which find the character 0 to 9 if it appears infront of a % symbol](./assets/images/bracket-3.png)

**```[^a-zA-Z]```** - matches all chracters that **are not upper and lower case characters**.
![image of the negation of expression](./assets/images/bracket-4.png)

### Greedy and Lazy Match
Greedy and Lazy match are two different ways a search is performed. The greedy mode is the default mode.

In a greedy mode the search is repeated as many times as possible without trying to match the rest of the pattern until the end of the text being searched through. After which the search checks the pattern and starts to backtrack until the end condition has been meet.

In the lazy mode ```?``` is added after a quantifier to specify that lazy mode is being activated. After every character match, the rest of the pattern is checked to see if they match as well.

Click [here](https://javascript.info/regexp-greedy-and-lazy) for a more detailed explanation to Greedy and Lazy match.

### Boundaries
A word boundary ```\b``` is similar to ```^``` and ```$```, in that the RegEx engine checks that the position in the string is a word boundary.

There are 3 different positions that qualify as word boundaries:
* At the start of a string, if the first string character is a word ```\w```.
* Between two characters in the string, where one is a word character ```\w``` and the other is not.
* At the end of the string, if the last string character is a word character ```\w```.

The following image shows an example:
![an image showing the word boundary](./assets/images/boundaries-1.png)

## Author
For any questions about the Gist, please don't hesitate to reach out.
* Link to my Github page : [ShawnMaz](https://github.com/ShawnMaz)
* Email: [shawnmaz@pm.me](mailto:shawnmaz@pm.me)
