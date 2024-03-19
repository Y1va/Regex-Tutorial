# Regular Expression Breakdown

This tutorial/breakdown will be a clear and concise guide to regular expressions, commonly known as 'Regex'. Regex is an essential tool when dealing with processing text, As a fundamental resource, regex enables developers to retrieve, modify and manipulate data within strings.

This Gist serves as a straight to the point breakdown to explain the idea behind regex.

## Summary

The Regex that I will be using for my breakdown will be the following: `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

The above regex can be used to match with a URL, a couple example URL's that match with the regex provided are: https://www.example.com/path/to/resource | http://subdomain.domain.co.uk/page1/page2

Do note that each description of the components will contain a code snippet, this is to demonstrate how each specific regex component can match with specific URL's. I will also be providing a console log which uses the regex test method after each code snippet which shows a boolean value of true highlighting if there is a match.

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
const regexQuantifiers = /^https?:\/\/([\w-]+\.)+[\w]{2,}(\/[\w-./?%&=]*)?$/;
const urlQuantifiers = 'https://www.example.com/path/to/resource?param1=value1&param2=value2';
console.log(regexQuantifiers.test(urlQuantifiers)); // Expected output: true
```


### Grouping Constructs

- `(...)` : The grouping constructs are defined by parenthesis and it denotes the beginning and end of a capturing group. These allow you to extract specific information from text efficiently.

The below code snippet shows 3 grouping constructs for the url https://www.example.com 

```javascript
const regexGroupConstructs = /^(https?):\/\/(www\.)?(example\.com)$/;
const urlGrouping = 'https://www.example.com';
const matchGrouping = urlGrouping.match(regexGroupConstructs)
console.log('Protocol:', matchGrouping[1]) // Expeted output: 'https'
console.log('Subdomain:', matchGrouping[2]) // Expected output: 'www.'
console.log('Top-Level Domain:', matchGrouping[3]) //Expected outpot: 'example.com'
```


### Bracket Expressions

- `[...]` : The square brackets match specific sets of characters in the input string, providing for a flexible way to specify patterns for matching.

The below code snippet shows the specificity that is needed to match for the subdomain. It is seen in the `[]`

```javascript
const regexBracketExpressions =  /^https?:\/\/[a-z0-44.-]+\.example\.com$/
const urlBracketExpressions = 'https://test-12.example.com'
console.log(regexBracketExpressions.test(urlBracketExpressions)) // Expected output: true
```


### Character Classes





### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
