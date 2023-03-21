# URL Matching - Using Regular Expressions

In this tutorial we will anzlyze the use and attributes of a regular expression written to match a sample URL based on a given criteria.

## Summary

The below code snippet represents a Regular Expression used to find a URL in a given set of text.

```md
const re = /^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```

In this iteration of a regular expression, we want to check a presented string for text that is formatted as a URL. Here the string will need to have the URL we are searching for at the very start of it. This is manipulated to be this way through "Anchors" used in the expression, which will be covered in greater detail later in this document.

In many applications, this can be useful when combined with the many methods that a regular expression can utilize. Some of these examples of these methods include...

    - exec()
    - match()
    - matchAll()
    - search()
    - replace()
    - replaceAll()

While we explore the different components of the expression it is important to note that what is being searched for is a correctly formatted URL. Meaning any text in that format will be matched to the criteria, however it does not mean it is a valid URL.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Character Escapes](#character-escapes)

## Regex Components

This particular regular expression uses many different components to define the terms for the search. In addition to the basic structure of the expression, it also utilizes anchors, quantifiers, grouping constructs, bracket expressions, character classes. Each of these components have unique ways of refining the search and help validate the structure of the text that is being searched to determine if it is a URL.

In many cases these components only apply to parts of the expression. For that reason we will look at each component, analyze what role it plays, where it is being applied, and what affect it has on the result.

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

The first of these two is the caret character ("^"). The first thing that we notice is that it is the only one in the expression, so it must have a unique and specific application. When the caret is used, the expression is being told that given a line of text, it should start its search at 'Position 0' in the string. Additionally if the text spans multiple lines, the expression will start its search at 'Line 1, Position 0. The sample text below demonstrates this with "[START]" marking where the expression will begin matching.

```md
const text = "[START]Somewhere over the rainbow,
where bluebirds fly."
```

The caret contrasts to other Anchors such as the '\A' anchor, which only starts the search at the beginning of the string.

The second of the two Anchors used, is the '$' character. This Anchor behaves similarly to the '^' anchor, but instead asserts the end of the string or line. Between these two we are able to define the searchable area for the expression.

### Quantifiers



### Grouping Constructs

### Bracket Expressions

Bracket Expressions are among the most flexible componeents of a regular expression. They are used to combine groups to create even more complex matching patterns. These groups consist of different character groups, which become the very basis of what dictates a matched character, or characters. There are many groups that are predfined, such as a group of all digits or alphanumeric characters. They can also identify specific special characters that can be matched as well.

If we look at our expression, we can identify these expressions wherever we see an opening and closing bracket. We will look at each bracket expression in our URL match expression below...

```md
const be1 = /[\da-z\.-]/
const be2 = /[a-z\.]/
const be3 = /[\/\w \.-]/
```

Let's examine the bracket expression be1 first. This expression can be broken up in to 3 groups. The first is '/d', which defines a subset of characters 0, 1, 2, 3, 4, 5, 6, 7, 8, and 9. It is important to note the backslash here. Without this backslash it would represent a single character 'd'. This is explained further in the "Character Escapes" section.

Also within be1, is the group 'a-z'. This group is relatively intuitive as is represents the 26 letters in the english alphabet.

Lastly we have two more character specifications, '/.' and '-'. As we alluded before these represent a single character that can be matched, which in this case are the characters '.' and '-' respectively. The '/.' specification, similar to the '/d' group will be further explained later.

### Character Classes

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
