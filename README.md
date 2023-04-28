# Regex tutorial

A regular expression, commonly referred to as regex or regexp, is a sequence of characters that define a search pattern. It is mainly used for text-based searching and string manipulation.

## Summary

Within this tutorial, I will go through regular expressions that are used in web development and how they are written in order to be used to find patterns in strings.

## Table of Contents

- [Regex tutorial](#regex-tutorial)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
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
  - [License](#license)
  - [Questions?](#questions)

## Regex Components

### Anchors

There are a few different types of anchors that you can use. There is ^, $, and \b. The ^ anchor matches the beginning of a line. The $ anchor matches the end of a line. The \b anchor matches a word boundary. Additionally, \d would match any digit and \w would match any alphanumeric character.

<mark>console.log(/^J/.test(str));</mark>

This piece of code would match any text that starts with the letter J because of the /^J/.

<mark>console.log(/t$/.test(str));</mark>

This piece of code would match any text that ends with the letter t.

Altogether, if we wanted to create a regular expression that would return all strings that contain the word cat, then our expression would look like this:

<mark>\w+cat\w+</mark>

### Quantifiers

Quantifiers allow you to specify how many characters or how many of a character class should be matched. By default, quantifiers are greedy, and will match as many characters as possible.

<mark>let pattern = /lo*/g;</mark>

This piece of code would allow the user to search for the letter l, followed by zero or more o characters.

Another type of quantifier is +, which allows you to match 1 or more times. And the ? quantifier allows you to match zero or one time. The ? quantifier makes it lazy because it causes the regular expression engine to match as few occurrences as possible.

### OR Operator

The OR operator within a regular expression is used by the | element. This expression returns either compenent that is seperated by the |. For example, abc|xyz would return either abc or xyz. This element can be used multiple times as well in the same expression. For example, <mark> abc | xyz | tuv </mark> would be a valid expression.

### Character Classes

With a character class or a character set, you can use regex to match only one out of several characters. For example, you can use this in gr[ae]y, which will match an a or e for a return of either gray or grey. However, this does not match graay, graey or any such thing. The order of the characters inside a character class does not matter. The results are identical. You can also use a hyphen inside to specify a range of characters. For example, [0-9] will match a single digit between 0 and 9.

### Flags

Regex expressions may have flags that affect the search. These flags allow you to change how the regex behaves, such as making it case-insensitive or allowing it to match on multiple lines. There are only 6 of them in JavaScript. There is i, g, m, s, u, and y. 

The i flag can be used in a search that is case-insensitive. Meaning that there is no difference between A and a.

The g flag can be used to search all matches, and without it, only the first match is returned.

The m flag performs multiline matches, which changes the behavior of ^ and $. If the m flag is used, ^ and $ match at the start or end of any line within the input string instead of the start or end of the entire string.

The s flag enables the "dotall" mode, which allows a dot . to match newline character.

The u flag enables full Unicode support. This means that characters of 4 bytes are handled correctly: as a single character, and not two 2 byte characters. Additionally, Unicode properties can be used in the search.

The y flag is "sticky" mode. This means that searching at the exact positon in the text.

### Grouping and Capturing

Capturing groups in regex are a way to treat multiple characters as a single unit. They are created by placing parentheses around a set of characters. By placing the a set of characters within parentheses, we create a group. For example, the regular expression (dog) creates a single group containing the letters "d" "o" and "g".

### Bracket Expressions

Bracket expressions will match anything within the brackets. For example, [abc] would match anything with a, b, or c.

### Greedy and Lazy Match

As previously mentioned, a greedy match tries to match an element as many times as possible. On the other hand, a lazy match tries to match an element as few times as possible. The ? is a lazy quantifier, whereas * is a greedy quanitfier.

### Boundaries

As previously mentioned, \b is an anchor that matches a word boundary. There are three different positions that qualify as word boundaries. One is before the first character in the string, or after the last character in the string, or between two characters in the string, where one is a word character and the other is not. To simplify, \b allows you to perform a "whole words only" search using a regular expression.

### Back-references

Back-references match the same text as previously matched by capturing a group. Back-references are specified with backslash and a single digit (e.g. ‘\1’). This expression will find the text matched by the first group in a regular expression. Another type of back-reference is a named backreference. This allows you to match the text that has been captured by a named group. If the same name has been used twice or more, the backreference will match the text from the most recent match. To define a named backreference, use "\k", followed by the name of the group.

### Look-ahead and Look-behind

Look-ahead and look-behind, collectively called “lookaround”, are zero-length assertions just like the start and end of line, and start and end of word anchors. The difference is that lookaround actually matches characters, but then gives up the match. Meaning it returns only the result match or no match. They don't consume characters in the string, but only assert whether a match is possible or not.

<mark>(?=foo)</mark>

This line of code asserts that what immediately follows the current position in the string is foo.

<mark>(?<=foo)</mark>

This line of code asserts that what immediately precedes the current position in the string is foo.

<mark>(?!foo)</mark>

This line of code asserts that what immediately follows the current position in the string is not foo.

<mark>(?<!foo)</mark>

This line of code asserts that what immediately precedes the current position in the string is not foo.

## License
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Questions?
- Github Profile: [https://github.com/mbatorek7](https://github.com/mbatorek7)
- Email: [maegan.batorek@valpo.edu](maegan.batorek@valpo.edu)