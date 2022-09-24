# Matching an Email Regex Tutorial

Hello World, I am Jon Cerruti, a Full Stack Web Developement Coding Bootcamp student. I have been tasked with developing a tutorial that explains how a specific regular expression, or "regex", functions by breaking down each part of the expression and describing what it does. I hope you enjoy my tutorial and gain some new knowledge along the way. Let's dive in!

![toddler dive](/bug-free-goggles/Develop/images/toddler-dive-child.gif)
## Summary

A regular expression or regex is a sequence of characters that defines a specific search pattern. In this tutorial I will be breaking down Matching an Email regex. This common regex is commonly used in validating an input.

An example of this regex is shown below: 
 

<code>
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
</code>



## Table of Contents
---
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)


## Regex Components
---
### Anchors
---
To create a regular expression in Javascript you must first enclose the pattern in forward slash charachters (/) like in our example Regex: 

- <code>/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/</code>

The next symbol inside of the forward slash we have a caret (^). The caret is called an anchor and it matches the beginning of the text. 
There is also another anchor in our regex and that is the dollar symbol ($). The dollar symbol is used to match the end of the text. You will use anchors to check if a string fully matches a pattern.

### Quantifiers
---

Quantifiers are used to quantify how many times a part of your regular expression should be repeated. Whenever it is neccessary to repeat something in a regex (single charachter, class of charachters, or a sub expression) you can specify this with a quantfier. The most common quantifiers are <code> ? * + {N} {,N} {N,} {N,M}</code> If we used the following  <code>abc+</code> in code, any string that begins in <code>ab</code> and is followed by at least one <code>c</code> will match.

If we look at a piece of our code: 
- <code>([a-z0-9_\.-]+)</code>

We can see that any string of letters a-z, numbers 0-9, underscore(_), period(.), or hyphen (-) will match. The square brackets define a set and are not a character in this case. The plus symbol (+) is our quantifier and signifies that the input must contain one of the previously defined characters in order to be a match. 


### Character Classes
---

A character class allows you to match any symbol from a certain character set. A character class is also called a character set. The most commonly used character classes are <code> \d \s \n \w </code> It is also common to combine charchter classes to create a more precise match. 

Looking at our regex:

- <code> @([\da-z\.-]+)\ </code>

We can identify one place where we have a character class. We have a <code>\d</code> right before <code>a-z\ .-</code>. This tells us that in addition to any lowercase letter a-z, a period, and a hyphen we may also have any number 0-9.



### Grouping and Capturing
---

A group in regular expression is a part of a regex pattern that is enclosed in parentheses () metacharacter. A group is formed by placing a regex pattern inside a set of parentheses. In our code 
<code>/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/</code> we can identify three groups:
- <code>([a-z0-9_\.-]+)</code>
- <code>([\da-z\.-]+)</code>
- <code>([a-z\.]{2,6})</code>

These 3 groups contain different patterns to match for each piece of code. The groups are divided by the "@", " \ ", and "." symbols. Typically a period "." is used in regex to match any single character, but it follows a backslash in this instance. The backslash " \ " is used as an escape key, and because we t want our "." to be taken literally. We don't want it to match the previous character, it should stand alone. 


### Bracket Expressions
---

Anything inside a set of square brackets ([]) represents a range of characters that we want to match. n our code we can identify three bracket expressions. 
- <code>/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/</code>


Our first bracket expression <code>[a-z0-9_\ .-]</code> may contain
- any letters a-z
- any number 0-9
- a hyphen "-"
- an underscore "_"
- a period "."

Our second bracket <code>[\da-z\ .-]</code> may contain
- any letters a-z
- a hyphen "-"
- a period "."

Our third bracket <code>[a-z\ .]</code>
- any letters a-z
- a period "."

### Greedy and Lazy Match
---

Just like we talked about in quantifiers earlier <code>([a-z0-9_\ .-]+)</code> The plus symbol (+) is our quantifier. It is quatifier that works in greedy mode. This just means that the quantifier will match its proceeding elements as much as possible.  



## Author
---
Thank you for reading along my attempt to explain Matching an Email regular expression. I really enjoyed learning a new topic and trying to teach my findings in this assigment. Feedback is always welcomed and appreciated. You can find my [Github here.](https://github.com/JonCerruti/Regex_Tutorial) Let's talk coding soon!