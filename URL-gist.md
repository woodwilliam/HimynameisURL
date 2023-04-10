# Hi My Name is URL

This a a Gist that breaks down a Regex for a URL matcher

## Summary

Matching a URL: `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/`

## Table of Contents

- [Section 1](#section-1)
- [Section 2](#section-2)
- [Section 3](#section-3)
- [Section 4](#section-4)
- [Author](#author)


## Regex Components

This Regex contians the following components:

`Anchors:` "^" and "$"
    Seen in Sections 1 and 4 respectivly
`Bracket Expression:` Contained within "[]"
    Seen in Sections 2, 3, and 4
`Grouping Constructs or "Catchgroup":` Contained within "()"
    Seen in Sections 1, 2, 3, 4
        Actually the parenthises are how Im dividing the diffrent sections
`Character Escapes:` there will be a "\" before the special charicter
    Seen in Sections 1, 2, 3, 4
`Character Classes:` there are a few of these and they are slightly less identifiable
    in this Regex we are using "/w" and "/d"
    Seen in Sections 2 and 4
    

### Section 1 

`^(https?:\/\/)?`
    the string starts with with a catch group.
        Inside the catcvhgorup there is lower case sensitive sequense of charicters "http"
        After that there is either be a lower case senstive charicter "s" or there will be nothing.
        After that there will the be the special chariceter ":" followled by 2 of the special charicter "/".
    This catch group will either be there or it will not.

Examples of Match:
``
`https://`
`http://`

`` works because of the ? quantifier nothing is an accaptable parameter.
`https://` & `http://` work because the http matches the literal parameters
    they also satisfy the ? quantifier
        Both having the 's' charicter at the end of 'http' and having nothing at the end of 'http' are accaptable parameters

Examples of not Match:
` `
`g`
`htytp:s//`
`egge`

` ` doesnt work because the character space (" ") is not one of the paramaters listed in the bracket expression
`/s` would be needed for space to be an available parameter
`g` & `egge` & `htytp:s//` dont work because they dont match the parameters that the catchgroupis looking for
they are neither nothing nor are they "http://" nor are they "https://"

### Section 2

`([\da-z\.-]+)\.`
    this catchgroup contains a bracket expression that contains:
        -number value of 0-9,
        -any lowercase charicter a-z, the special charicter "." and the special charicter "-"
    this will happen at least one time

Examples of Match:
`h.y`
`8`
`g6`

`h.y` works because the characters are lowercase and a-z, "." is an accepted special character
`g6` works because it has a lowercase a-z chracter and a character with a number value of 0-9
`8` works because it has a character with a number value of 0-9
    and it allowed to be a single character becuse of the "+" quantifier

Examples of not Match:
``
` `
`Hg`
`!!dgd`

`` doesn't work because of the + quantifier
` ` doesnt work because the character space (" ") is not one of the paramaters listed bracket expression
`Hg` doesnt work because H is not a lowercase character
`!!dgd` doesn't work because the "!" charicter is not one of the special characters listed in the bracket expression

### Section 3

`([a-z\.]{2,6})`
the catchgroup contains a bracket expression that contains:
    any lowercase sensitive charicter a-z
    the special character "."
the `{2,6}` quantifier gives character limit on the catchgroup with a min of 2 and a max of 6

Examples of Match:
`burp.`
`.g`
`cheese`

`burp.` & `.g` work because they satisfies the character limit parameters
    "burp" are all a-z characters and "." works because it was provided in the bracket expression
    the same for "g" and "."

Examples of not Match:
``
`.`
`.cheese`
`.G`

`` doesn't work because there is not a quantifier indicating that nothing is an option
`.` & `.cheese` dont work because they dont satisfy the character limit
    `.` is under 2 characters
    `.cheese` is over 6 characters
`.G` doesn't work because G is not a lowercase character

### Section 4

`([\/\w \.-]*)*\/?$/`
the catchgroup contains a bracket expression that contains:
    the "/" special character
    any word character (alpha-numeric and upper or lowercase)
    the "." special character
    the "-" special character
after the brackter expression there is a "*" quantifier
    this means that everything contained in the bracket expression can happen between 0-infinity times
after the catchgroup there is a "*" quantifier
    this means that the content produced within the catchgroup can happen between 0-infinity times
folowing the quantifier there is a "/" special character follwed by a ? quantifier
    this means that the "/" can occur zero or 1 time
following the quantifier there is a $ anchor
    this means that the string has ended

Examples of Match:

``
`///frogkhlh//7484iuHJSLDKFRHLF////`

`///frogkhlh//7484iuHJSLDKFRHLF////` works because the "/" special character is allowed
    `frogkhlh` & `7484iuHJSLDKFRHLF` are both considered a word
    the "*" quantifier means that you can have mutiple words and "/" special charcter 
`` works because the "*" quantifier allows nothing as an option

`///frogkhlh//7484iuHJSLDKFRHLF//@#$$$#//`
    this doesn't work because the spcial characters "@", "#", and "$" are not listed in the available parameters


### Author

William Wood is a student attending the Fullstack Bootcamp at University of Minnesota.

Github: https://github.com/woodwilliam
