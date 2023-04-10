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