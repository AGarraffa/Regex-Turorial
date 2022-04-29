# RegEx tutorial

For this assignment we were tasked with doing some light research on a coding/CS topic. I began to do some light research on React, knowing that we would be covering this later in the course and wanting to get a head start on using it. While conceptually I was following the tutorials without too much difficulty, it became increasing harder to go through the tutorials without plagiarizing them. So, like any good student, I decided to take the easy way out and follow the example on regex (granted regex had come up a few times while working on assignments so it's not a bad idea for me to actually familiarize myself with the concept).


## Table of Contents
- [What is regex](#what-is-regex)
- [How to use regex](#how-to-use-regex)
- [Bracket Expressions](#bracket-expressions)
- [Subexpressions and Operators](#subexpressions-and-operators)
- [Quantifiers](#quantifiers)
- [Anchors](#anchors)
- [Flags](#flags)
- [Bringing it all together](#bringing-it-all-together)
- [Sources](#sources)
- [Author](#author)

## What is regex

Regex (short for regular expression) is a way to create a generalized search algorithm when you want to search for a format of characters, as opposed to something specific. 


## How to use regex

A regex is written using a series of special characters that represent the characters in the search that you want to run, and wrapped in slashes (/). To get started, first identify the pattern or format of characters you are wanting to search for (ex: phone numbers). 


## Bracket Expressions 

Wrapping a character type in brackets (known as a bracket expression) you can search for that character type: [abc] will look for a string that includes (but not exclusively) a, b, or c. Using a hyphen will allow you to use a range of characters, rather than having to type out each one: [a-zA-z0-9] will include all upper and lower case letters as well as numbers 0 through 9. Adding a ^ symbol within the brackets will exclude those characters, rather than include. 


## Subexpressions and Operators

Bracket expressions look for a group of characters, but wrapping a set of characters in parentheses will look for an exact match. (Dog) will look for exactly Dog (case sensitive). 

Using the vertical bar (|) is akin to the word or. (D|o|g) is looking for D or o or g. In this case, Dgo would be acceptible (similar to using [Dog]).

Using a backslash (\) essentially negates the special meaning of a symbol within a regex. If you are looking to include an open bracket you would want to use \[. This would negate the normal meaning of an open bracket (ie beginning a bracket expression).

Finally, character classes can be used to cover a wide range of characters. 

. will match any character (except the newline \n character).

\d is any digit 0-9 (which is the same as writing [0-9]).

\w is the equivalent of writing [A-Za-z0-9_]; any letter in the basic alphabet (upper and lower case), 0 through 9, and the underscore. 

\s looks for whitespace characters (spaces, tabs, and line breaks).

Capitalizing any of the previous characters looks for the opposite (ie /D looks for non numbers).


## Quantifiers

Quantifiers allow you to determine the number of times you want your pattern to match. 

Using * (matches zero or more times)

Using + (matches one or more times)

Using ? (matches the pattern zero or one time)

In addtion to those symbols braces ({}) and numbers can be used to match the pattern a certain number of times (depending on what is included in the braces). {2} means the regex will match the pattern exactly two times. {2, 10} will match at least 2 times and at most 10. Using this example: [a-zA-z0-9] the pattern being searched on is any alphanumeric character. So [a-zA-z0-9]{2, 10} effectively translates to the string being between 2 and 10 characters long. Finally, you can use a ? after any  of the quantifiers which will make it 'lazy' and match the fewest occurances as possible (as opposed to matching as many occurances as possible, also known as 'greedy').


## Anchors

Anchors are used to determine whether the string starts or ends with a specific character type.The ^ symbol requires that the string begins with a specific character type, and the $ requires that it ends with one. ^[0-9] would require that the string begins with a number while [0-9]$ requires the string ends with a number. ^[0-9]$ would require the string start and end with a number. 



## Flags

Instead of wrapping the regex in slashes, you may also use flags, which are placed at the end of the expression after the second slash. 

g is a Global search and tests the expression against all possible matches

i allows the regex to be case insensitive

m allows you to use multiple lines within the regex and treat it as such while searching. 


## Bringing it all together

Let's say your company email ends in @company.com and you want to verify that an input includes one of those emails. Your regex would look something like this:

/(^[a-zA-Z0-9-_](@company.com)$)

This only includes emails with alphanumeric characters as well as a hyphen or underscore within the email name and then ends with @company.com.

Alternitively you can use:

/(^\w(@company.com)$)


## Sources

w3Schools
MDN Web Docs
The Coding Train (YT)
https://coding-boot-camp.github.io/full-stack/

## Author
Alfred Garraffa
https://github.com/AGarraffa