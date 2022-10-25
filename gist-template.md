# RegEx Review

Regular Expressions or RegEx or RegExp help extract specific information from a given piece of text. It is used to locate or validate a string from a given text. Almost all programming languages support RegEx. This document is meant to be a quick cheatsheet of some of the most used Regular Expressions.

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.



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

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
