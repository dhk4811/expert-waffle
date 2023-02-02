# expert-waffle

# You Don't Know JS Yet

## Scope

Things to know about javascript before proceeding

functions are first-class values
can be assigned and passed around just like number or strings

closure
they maintain their original scope no matter where in the program the functions are eventually executed

Modules
code organization pattern characterized by public methods that have privileged access to hidden variables and functions in the internal scope of the module


Compiled vs. Intepreted
compilation: whole source code is transformed at once
resulting instructions are saves as output that can later be executed


interpretation: source code is transformed line by line

but numerous variations of both compilation and interpretation exist

*scope* is determined during compilation
1. tokenizing/lexing: break up a string of characters into meaningful chunks (tokens)

ex) var a = 2;
is broken up into the following tokens: var, a, =, 2 and ;

2. parsing: taking a stream of tokens and tuning it into a tree of nested elements

Abstract Syntax Tree: collectively represent the grammatical structure of the program

a tree as such could be 
VariableDeclaration(var) - Identifier(a) - AssignmentExpression(=) - NumericLiteral(2)

3. Code Generation
takings the AST and turning it into executable code.

JS -> compilation must happen in mere microseconds

the processing of JS programs occurs in two phases

parsing/compilation first, then execution

syntax errors, early errors, and hoisting all prove the existence of the two phases

**Syntax Errors**
```
var greeting = "Hello";
console.log(greeting);
greeting = ."Hi";
```

-> this code throws a SyntaxError about the unexpected . before the "Hi" string.
-> the console.log(..) function is not executed because JS first parses the entire program before execution


**Early Errors**
in strictmode -> duplicate parameter names are not allowed

```
saySomething("Hello", "Hi");

function saySomething(greeting, greeting) {
  "use strict";
  console.log(greeting);
}
```
Hoisting

```
function saySomething() {
  var greeting = "Hello";
  {
    greeting = "Howdy";
    let greeting = "Hi";
    console.log(greeting);
  }
}

saySomething();
```

JS engine knows that a blocked-scoped variable with the same name will be declared.

thus JS programs are parsed before any execution begins

---

CSS

CSS specificity

when the specificity values are exactly the same
the one further down wins 

```
<ul id="summer-drinks">
   <li class="favorite">Whiskey and Ginger Ale</li>
   <li>Wheat Beer</li>
   <li>Mint Julip</li>
</ul>
```

```
ul#summer-drinks li {
   font-weight: normal;
   font-size: 12px;
   color: black;
}
```

```
.favorite {
  color: red;
  font-weight: bold;
}
```

```
ul#summer-drinks li.favorite {
  color: red;
  font-weight: bold;
}
```

another way is to use the !important declaration

```
.favorite {
  color: red !important;
  font-weight: bold !important;
}
```

Calculating CSS Specificity Value

more to least
style attribute -> id -> class, pseudo-class attribute -> elements

element with inline styling wins, equivalent to 1000 points
each id value, is given 100 points
each class value, 10 points
each element reference, 1 point

it could also be thought as a vector [0, 0, 0, 0] since a css that specifies 13 elements is not considered
more specific than a css that specifies a class









ID selectors
most powerful type of selector in terms of CSS specificity

Normal Flow
If there is no CSS applied to change the layout


CSS Transitions

transition-property: property; 
transition-duration: duration;
transition-timing-function: timing-fuction;

---

CSS terms

1 em
unit of measurement, relative to the size of the font

historically the em unit was named after the width of the capital "M"

inline
: take up as much width as necessary, placed inline with the text and other elements around it.

block
: take up the full width of container

---

CSS Grid Layout

define container element as grid using `display: grid`
to set the column size: `grid-template-columns`
to set the row size: `grid-template-rows`

grid-columns
grid-row

grid line
: dividing lines that make up the structure of the grid

grid track
: space between two adjacent grid lines (columns or row of a grid)

grid area
: the total space surrounded by four grid lines

grid cell
: space between two adjacent row and two adjacent column grid lines


----

add new element to HTML DOM in JavaSript

createElement()
- create an eleemnt

`document.createElement(tagName)`

appendChild()
- add it to the HTML DOM


-- 

CSS Transitions

you can create CSS Transitions with the transition property

```
.selector {
  transition: property duration transition-timing-function delay;
}
```

transition is the shorthand for 
transition-property 
transition-duration
transition-timing-function
transition-delay

