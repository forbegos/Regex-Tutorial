# Regex-Tutorial URL Parser

## Summary

This gist is a tutorial and explanation on how the URL Parser REGEX works:

```
/^(https?\:)\/\/(([^:\/?#]*)(?:\:([0-9]+))?)([\/]{0,1}[^?#]*)(\?[^#]*|)(#.*|)$/
```

## What is a Regex

Regex is short for Regular Expression. Basically it is a sequence of characters that is used as a search pattern. These patterns allow
to match, locate or manage strings. Regular expressions have been used in the world of programming since around 1970.

As Ken Thompson describes:

“A regular expression is a pattern which specifies a set of strings of characters; it is said to match certain strings.” —Ken Thompson

Understanding regular expressions can be a bit cumbersome. In this gist we will attemp to describe the URL Parser regular expression and
how it works.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Explanation

/
^(https\:)\/\/(([^:\/?#])(?:\:([0-9]))?)([\/][^?#])(\?[^#]|)(#.|)$
/
^ asserts position at start of the string
1st Capturing Group (https\:)
http matches the characters http literally (case sensitive)
s matches the character s literally (case sensitive)
? matches the previous token between zero and one times, as many times as possible, giving back as needed (greedy)
\: matches the character : literally (case sensitive)
\/ matches the character / literally (case sensitive)
\/ matches the character / literally (case sensitive)
2nd Capturing Group (([^:\/?#])(?:\:([0-9]))?)
3rd Capturing Group ([^:\/?#])
Match a single character not present in the list below [^:\/?#]

- matches the previous token between zero and unlimited times, as many times as possible, giving back as needed (greedy)
  : matches the character : literally (case sensitive)
  \/ matches the character / literally (case sensitive)
  ?# matches a single character in the list ?# (case sensitive)
  Non-capturing group (?:\:([0-9]))?
  ? matches the previous token between zero and one times, as many times as possible, giving back as needed (greedy)
  \: matches the character : literally (case sensitive)
  4th Capturing Group ([0-9])
  5th Capturing Group ([\/][^?#])
  Match a single character present in the list below [\/]
  {0,1} matches the previous token between zero and one times, as many times as possible, giving back as needed (greedy)
  \/ matches the character / literally (case sensitive)
  Match a single character not present in the list below [^?#]
- matches the previous token between zero and unlimited times, as many times as possible, giving back as needed (greedy)
  ?# matches a single character in the list ?# (case sensitive)
  6th Capturing Group (\?[^#]|)
  1st Alternative \?[^#]
  \? matches the character ? literally (case sensitive)
  Match a single character not present in the list below [^#]
  2nd Alternative — null, matches any position
  7th Capturing Group (#.|)
  1st Alternative #.
  '# matches the character # literally (case sensitive)
  . matches any character (except for line terminators)
  2nd Alternative — null, matches any position
  $ asserts position at the end of the string, or before the line terminator right at the end of the string (if any)

### Anchors

- Start of match: \G
- Start of string: ^
- End of string: $
- Start of string: \A
- End of string: \Z
- Absolute end of string: \z
- A word boundary: \b
- Non-word boundary: \B

### Quantifiers

- Zero or one of a: a?
- Zero or more a: a\*
- One or more of a: a+
- Exactly 3 of a: a{3}
- 3 or more of a: a{3,}
- Between 3 and 6 of a: a{3,6}
- Greedy quantifier: a\*
- Lazy quantifier: a\*?
- Possesive quantifier: a\*+

### Grouping Constructs

- Lookbehind … (?(?<=...)yes|no)
- Recurse entire pattern (?R)
- Recurse first subpattern (?1)
- Recurse first relative subpat… (?+1)
- Recurse subpattern `na… (?&name) Match subpattern `na… (?P=name)
- Recurse subpattern ca… (?P>name)
- Pre-define patte… (?(DEFINE)...)
- Positive Lookahead (?=...)
- Negative Lookahead (?!...)
- Positive Lookbehind (?<=...)
- Negative Lookbehind (?<!...)
- Control verb (\*ACCEPT)
- Control verb (\*FAIL)
- Control verb (\*MARK:NAME)
- Control verb (\*COMMIT)
- Control verb (\*PRUNE)
- Control verb (\*SKIP)

### Bracket Expressions

A single character of: a, b or c [abc]
A character except: a, b or c [^abc]
A character in the range: a-z [a-z]
A character not in the range: a-z [^a-z]
A character in the range: a-z or A-Z [a-zA-Z]
Letter and digits [:alnum:]]
Letters [[:alpha:]]
ASCII codes 0-127 [[:ascii:]]
Space or tab only [[:blank:]]
Control characters [[:cntrl:]]
Decimal digits [[:digit:]]
Visible characters (not space) [[:graph:]]
Lowercase letters [[:lower:]]
Visible characters [[:print:]]
Visible punctuation characters [[:punct:]]
Whitespace [[:space:]]
Uppercase letters [[:upper:]]
Word characters [[:word:]]
Hexadecimal digits [[:xdigit:]]
Start of word [[:<:]]

### Character Classes

- A single character of: a, b or c [abc]
- A character except: a, b or c [^abc]
- A character in the range: a-z [a-z]
- A character not in the rang… [^a-z]
- A character in the range… [a-zA-Z]
- Letters and digits [[:alnum:]]
- Letters [[:alpha:]]
- ASCII codes 0-127 [[:ascii:]]
- Space or tab only [[:blank:]]
- Control characters [[:cntrl:]]
- Decimal digits [[:digit:]]
- Visible characters (n… [[:graph:]]
- Lowercase letters [[:lower:]]
- Visible characters [[:print:]]
- Visible punctuation … [[:punct:]]
- Whitespace [[:space:]]
- Uppercase letters [[:upper:]]
- Word characters [[:word:]]
- Hexadecimal digits [[:xdigit:]]

### Flags

- Global g
- Multiline m
- Case insensitive i
- Ignore whitespace / verbose x
- Single line s
- Unicode u
- eXtra X
- Ungreedy U
- Anchor A
- Duplicate group names J

## Author

Fernando de Orbegos is a full stack web developer. You can learn more about his projects at: https://github.com/forbegos
