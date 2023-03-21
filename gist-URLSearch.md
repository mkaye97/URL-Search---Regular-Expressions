# URL Matching - Using Regular Expressions

In this tutorial we will anzlyze the use and attributes of a regular expression written to match a sample URL based on a given criteria.

## Summary

The below code snippet represents a Regular Expression used to find a URL in a given set of text.

```md
const re = /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```

In this iteration of a regular expression, we are using it to check a presented string for text that is formatted as a URL. Here the string will need to have the URL we are searching for at the very start of it. This is manipulated to be this way through "Anchors" used in the expression, which will be covered in greater detail later in this document.

In many applications, this can be useful when combined with the many methods that a regular expression can utilize. Many of these Examples of these methods include...

    - exec()
    - match()
    - matchAll()
    - search()
    - replace()
    - replaceAll()
    - etc.

While we explore the different components of the expression it is important to note that what is being searched for is a correctly formatted URL. Meaning any text in that format will be matched to the criteria, however it does not mean it is a valid URL.

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

This particular regular expression uses many different components to define the terms for the search. In addition to the basic structure of the expression, it also utilizes anchors, quantifiers, grouping constructs, bracket expressions, character classes. Each of these components have unique ways of refining the search and help validate the structure of the text that is being searched to determine if it is a URL.

In many cases these components only apply to parts of the expression. For that reason we will look at each component, and analyze what type of component it is, and additionally where it is being applied, and what affect it has on the result.

### Anchors
A Regular Expression can sometimes use an "Anchor" to assert where in a string the desired search content should be. There are many different characters which all represent different positions in the string that we want to search for a given criteria, and specific conditions that they should be used under. Let us look at our expression...

```md
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```

Now we will look at both the ending and beginning sections of the expression...

```md
/^(https?:\/\/)?/ -------- /([\/\w \.-]*)*\/?$/
```

In these sections of the code we can identify two Anchors.

The first of these two is the caret character ("^"). The first thing that we notice is that it is the only one in the expression, so it must have a unique and specific application. When the caret is used the expression is being told that given a line of text, it should start its search at 'Position 0' in the string. Additionally if the text spans multiple lines, the expression will start its search at 'Line 1, Position 0. The sample text below demonstrates this marking the start.

```md
const text = "[START]Somewhere over the rainbow,
where bluebirds fly."
```

The caret contrasts to other Anchors such as the '\A' anchor, which only starts the search at the beginning of the string.

The second of the two Anchors used, is the '$' character. This Anchor behaves similarly to the '^' anchor, but instead denotes the end of the string or line. Between these two we are able to define the searchable area for the expression.

### Quantifiers



### Grouping Constructs

### Bracket Expressions

### Character Classes

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
