# Regular Expression Breakdown

This tutorial/breakdown will be a clear and concise guide to regular expressions, commonly known as 'Regex'. Regex is an essential tool when dealing with processing text, As a fundamental resource, regex enables developers to retrieve, modify and manipulate data within strings.

This Gist serves as a straight to the point breakdown to explain the idea behind regex.

## Summary

The Regex that I will be using for my breakdown will be the following: `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

The above regex can be used to match with a URL, a couple example URL's that match with the regex provided are: https://www.example.com/path/to/resource | http://subdomain.domain.co.uk/page1/page2

Do note that each description of the components will contain a code snippet, this is to demonstrate how each specific regex component can match with specific URl's. I will also be providing a console log after each code snippet which shows a boolean value of true highlighting there is a match.

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

- `^` : The caret anchor represents the start of a line
- `$` : The dollar sign represents the end of a line

```javascript
const regexAnchors = /^https?:\/\/example\.com$/;
const urlAnchors = 'https://example.com';
console.log(regexAnchors.test(urlAnchors)); // Expected output: true
```

### Quantifiers

- `?` : The question mark means 0 or 1 of the preceeding element. It makes the preceeding element optional.
- `+` : The plus sign indicates that the preceeding element can occur one or more times. 
- `*` : The asterisk indicates that the preceeding element can occur 0 or more times

The below code snippet utilises the ?, +, and the * Quantifiers, it also shows the string/URL that the regex matches with.

```javascript
const regexQuantifiers = /^https?:\/\/([\w-]+\.)+[\w]{2,}(\/[\w-./?%&=]*)?$/
const urlQuantifiers = 'https://www.example.com/path/to/resource?param1=value1&param2=value2'
console.log(regexQuantifiers.test(urlQuantifiers)) // Expected output: true
```

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
