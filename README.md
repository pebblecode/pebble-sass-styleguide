# pebble {code} Sass Style Guide

This documents outlines best practices for writting Sass at pebble {code}

Adapted from Nicolas Gallagher's [idiomatic-css](https://github.com/necolas/idiomatic-css)

## Table of contents

1. [General Principles](#general-principles)
2. [Whitespace](#whitespace)
3. [Comments](#comments)
4. [Format](#format)
5. [Practical Example](#example)

<a name="general-principles"></a>
## 1. General Principles

* Don't try to prematurely optimize your code; keep it readable and
  understandable. For CSS/Sass readability is generally more important than performance.
* All code in any code-base should look like a single person typed it, even
  when many people are contributing to it.
* Strictly enforce the agreed-upon style.
* If in doubt when deciding upon a style use existing, common patterns.
* Use [Sass](http://sass-lang.com) and the [SCSS syntax](http://sass-lang.com/documentation/file.INDENTED_SYNTAX.html#sass_syntax_differences) for all CSS tasks.
* Never use IDs for styling purposes. Always use classes instead.
* Use hyphens rather than underscores to separate class/variable names.
* Use Hex or HSL colors where possible. Only use RGB colors when you need to use semi transparent colors.


<a name="whitespace"></a>
## 2. Whitespace

* Use soft-indents (spaces)
* Each level of indentation should be 2 spaces


<a name="comments"></a>
## 3. Comments

Aim to write code that is self documenting and easy to understand. However sometimes comments will be useful for yourself or other developers. For example

* To document unusual behavior.
* To show browser/bug fixes.
* To show something as uncompleted.

Use the Sass Syntax for comments `// comment`<br />
**DO NOT** use the CSS syntax for comments `/* comment */`


<a name="formating"></a>
## 4. Formating

* Each `.scss` file should have a title and a description of it's contents.
* Use one discrete selector per line in multi-selector rulesets.
* Include a single space before the opening brace of a ruleset.
* Include one declaration per line in a declaration block.
* Use one (two spaces) level of indentation for each declaration.
* Include a single space after the colon of a declaration.
* Use lowercase and shorthand hex values, e.g., `#aaa`.
* Use double quotes wherever possible, e.g., `content: ""`.
* Quote attribute values in selectors, e.g., `input[ type="checkbox" ]`.
* Avoid specifying units for zero-values, e.g., `margin: 0`.
* Include a space after each comma in comma-separated property or function values.
* Include a semi-colon at the end of the last declaration in a declaration block.
* Place the closing brace of a ruleset in the same column as the first character of the
* Separate each ruleset by a blank line.
* Put spaces inside brackets for better readability.
* Leave a new line after each nested ruleset.
* Limit nesting to 3 level deep absolute maximum.
* Avoid large numbers of nested rules. Break them up when readability starts to
  be affected.

#### Declaration order

Declaration order should be as follows...

* Scoped variables.
* New line.
* @extend
* @import
* New line
* All rules for top-level selector
* New line
* Any nested elements
* New line
* Any pseudo classes e.g.`:hover, :focus, ::before, ::after`
* New line
* Any media queries

#### Exceptions and slight deviations

Large blocks of single declarations can use a slightly different, single-line
format. In this case, a space should be included after the opening brace and
before the closing brace.

```scss
.selector-1 { width: 10%; }
.selector-2 { width: 20%; }
.selector-3 { width: 30%; }
```

Long, comma-separated property values - such as collections of gradients or
shadows - can be arranged across multiple lines in an effort to improve
readability and produce more useful diffs. There are various formats that could
be used; one example is shown below.

```scss
.selector {
  background-image: linear-gradient(#fff, #ccc),
                    linear-gradient(#f3c, #4ec);
  box-shadow: 1px 1px 1px #000,
              2px 2px 1px 1px #ccc inset;
}
```

<a name="example"></a>
## 5. Example SCSS

Examples of all the above formating guides can be found in `examples.scss`.

Based on a work at
[github.com/necolas/idiomatic-css](https://github.com/necolas/idiomatic-css).
