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