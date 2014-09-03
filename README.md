# pebble {code} CSS & Sass Style Guide

This documents outlines best practices for writting CSS & Sass @ pebble {code}

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
* Use [Sass](http://sass-lang.com) and the [SCSS syntax](http://sass-lang.com/documentation/file.INDENTED_SYNTAX.html#sass_syntax_differences).
* Never use IDs for styling purposes. Always use classes instead.


<a name="whitespace"></a>
## 2. Whitespace

* Use soft-indents (spaces)
* Each level of indentation should be 2 spaces


<a name="comments"></a>
## 3. Comments

Aim to write code that is self documenting and easy to understand. However sometimes comments will be useful for yourself or other developers. For example

Use the Sass Syntax for comments `// comment`<br />
**DO NOT** use the CSS syntax for comments `/* comment */`


<a name="format"></a>
## 4. Format

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
* Use hyphens rather than underscores to separate class/variable names
* Exceptions and slight deviations

```css
/* Use one discrete selector per line in multi-selector rulesets. */
/* ========================================================================== */
/* incorrect */
.class-one, .class two {
  /* rules */
}

/* correct */
.class-one,
.class two {
  /* rules */
}

/* Include a single space before the opening brace of a ruleset. */
/* ========================================================================== */
/* incorrect */
.class-one{
  /* rules */
}

/* correct */
.class-one {
  /* rules */
}

/* Include one declaration per line in a declaration block. */
/* ========================================================================== */
/* incorrect */
.class-one{
  width: 100%; height: 100%;
}

/* correct */
.class-one {
  width: 100%;
  height: 100%;
}

/* Use one (two spaces) level of indentation for each declaration. */
/* ========================================================================== */
/* incorrect */
.class-one{
  width: 100%;
    height: 100%;
padding: 10%;
}

/* correct */
.class-one {
  width: 100%;
  height: 100%;
  padding: 10%;
}

/* Include a single space after the colon of a declaration. */
/* ========================================================================== */
/* incorrect */
.class-one{
  width:100%;
}

/* correct */
.class-one {
  width: 100%;
}

/* Use lowercase and shorthand hex values, e.g., `#aaa`. */
/* ========================================================================== */
/* incorrect */
.class-one{
  background-color: #EE4F7E;
  color: #F09;
}

/* correct */
.class-one {
  background-color: #ee4f7e;
  color: #f09;
}

/* Use double quotes wherever possible, e.g., `content: ""`. */
/* ========================================================================== */
/* incorrect */
.class-one{
  background-image: url( 'img/pic.jpg' );
}

/* correct */
.class-one {
  background-image: url( "img/pic.jpg" );
}

/* Quote attribute values in selectors, e.g., `input[ type="checkbox" ]`. */
/* ========================================================================== */
/* incorrect */
input[ type=checkbox ] {
  /* rules */
}

/* correct */
input[ type="checkbox" ] {
  /* rules */
}

/* Avoid specifying units for zero-values, e.g., `margin: 0`. */
/* ========================================================================== */
/* incorrect */
.class-one {
  margin: 0px;
  padding: 0%;
}

/* correct */
.class-one {
  margin: 0;
  padding: 0;
}

/* Include a space after each comma in comma-separated property or function values. */
/* ========================================================================== */
/* incorrect */
.class-one {
  color: hsl( 180,50,100 );
}

/* correct */
.class-one {
  color: hsl( 180, 50, 100 );
}

/* Include a semi-colon at the end of the last declaration in a declaration block. */
/* ========================================================================== */
/* incorrect */
.class-one {
  width: 100%;
  height: 100%;
  margin: 20px
}

/* correct */
.class-one {
  width: 100%;
  height: 100%;
  margin: 20px;
}

/* Place the closing brace of a ruleset in the same column as the first character of the ruleset. */
/* ========================================================================== */
/* incorrect */
.class-one {
  width: 100%;
  height: 100%; }

/* incorrect */
.class-one {
  width: 100%;
  height: 100%;
  }

/* correct */
.class-one {
  width: 100%;
  height: 100%;
}

/* Separate each ruleset by a blank line. */
/* ========================================================================== */
/* incorrect */
.class-one {
  width: 100%;
  height: 100%;
}
.class-two {
  margin: 10%;
  padding: 10%;
}

/* correct */
.class-one {
  width: 100%;
  height: 100%;
}

.class-two {
  margin: 10%;
  padding: 10%;
}

/* Put spaces inside brackets for better readability. */
/* ========================================================================== */
/* incorrect */
.class-one {
  color: hsl(180, 100, 50);
}

/* correct */
.class-one {
  color: hsl( 180, 100, 50 );
}

/* Use hyphens rather than underscores to separate class/variable names */
/* ========================================================================== */
/* incorrect */
.class_one {
  /* rules */
}

/* correct */
.class-one {
  /* rules */
}
```

#### Exceptions and slight deviations

Large blocks of single declarations can use a slightly different, single-line
format. In this case, a space should be included after the opening brace and
before the closing brace.

```css
.selector-1 { width: 10%; }
.selector-2 { width: 20%; }
.selector-3 { width: 30%; }
```

Long, comma-separated property values - such as collections of gradients or
shadows - can be arranged across multiple lines in an effort to improve
readability and produce more useful diffs. There are various formats that could
be used; one example is shown below.

```css
.selector {
  background-image: linear-gradient(#fff, #ccc),
                    linear-gradient(#f3c, #4ec);
  box-shadow: 1px 1px 1px #000,
              2px 2px 1px 1px #ccc inset;
}
```

### Preprocessors: additional format considerations

Different CSS preprocessors have different features, functionality, and syntax.
Your conventions should be extended to accommodate the particularities of any
preprocessor in use. The following guidelines are in reference to Sass.

* Limit nesting to 1 level deep. Reassess any nesting more than 2 levels deep.
  This prevents overly-specific CSS selectors.
* Avoid large numbers of nested rules. Break them up when readability starts to
  be affected. Preference to avoid nesting that spreads over more than 20
  lines.
* Always place `@extend` statements on the first lines of a declaration
  block.
* Where possible, group `@include` statements at the top of a declaration
  block, after any `@extend` statements.
* Consider prefixing custom functions with `x-` or another namespace. This
  helps to avoid any potential to confuse your function with a native CSS
  function, or to clash with functions from libraries.

```scss
.selector-1 {
    @extend .other-rule;
    @include clearfix();
    @include box-sizing(border-box);
    width: x-grid-unit(1);
    /* other declarations */
}
```


<a name="example"></a>
## 5. Practical example

An example of various conventions.

```css
/* ==========================================================================
   Grid layout
   ========================================================================== */

/**
 * Column layout with horizontal scroll.
 *
 * This creates a single row of full-height, non-wrapping columns that can
 * be browsed horizontally within their parent.
 *
 * Example HTML:
 *
 * <div class="grid">
 *     <div class="cell cell-3"></div>
 *     <div class="cell cell-3"></div>
 *     <div class="cell cell-3"></div>
 * </div>
 */

/**
 * Grid container
 *
 * Must only contain `.cell` children.
 *
 * 1. Remove inter-cell whitespace
 * 2. Prevent inline-block cells wrapping
 */

.grid {
    height: 100%;
    font-size: 0; /* 1 */
    white-space: nowrap; /* 2 */
}

/**
 * Grid cells
 *
 * No explicit width by default. Extend with `.cell-n` classes.
 *
 * 1. Set the inter-cell spacing
 * 2. Reset white-space inherited from `.grid`
 * 3. Reset font-size inherited from `.grid`
 */

.cell {
    position: relative;
    display: inline-block;
    overflow: hidden;
    box-sizing: border-box;
    height: 100%;
    padding: 0 10px; /* 1 */
    border: 2px solid #333;
    vertical-align: top;
    white-space: normal; /* 2 */
    font-size: 16px; /* 3 */
}

/* Cell states */

.cell.is-animating {
    background-color: #fffdec;
}

/* Cell dimensions
   ========================================================================== */

.cell-1 { width: 10%; }
.cell-2 { width: 20%; }
.cell-3 { width: 30%; }
.cell-4 { width: 40%; }
.cell-5 { width: 50%; }

/* Cell modifiers
   ========================================================================== */

.cell--detail,
.cell--important {
    border-width: 4px;
}
```


## Translations

* [Bahasa Indonesia](https://github.com/necolas/idiomatic-css/tree/master/translations/id-ID)
* [Česky](https://github.com/necolas/idiomatic-css/tree/master/translations/cs-CZ)
* [Dansk](https://github.com/necolas/idiomatic-css/tree/master/translations/da-DK)
* [Deutsch](https://github.com/necolas/idiomatic-css/tree/master/translations/de-DE)
* [Español](https://github.com/necolas/idiomatic-css/tree/master/translations/es-ES)
* [Français](https://github.com/necolas/idiomatic-css/tree/master/translations/fr-FR)
* [Italiano](https://github.com/necolas/idiomatic-css/tree/master/translations/it-IT)
* [日本語](https://github.com/necolas/idiomatic-css/tree/master/translations/ja-JP)
* [한국어](https://github.com/necolas/idiomatic-css/tree/master/translations/ko-KR)
* [Nederlands](https://github.com/necolas/idiomatic-css/tree/master/translations/nl-NL)
* [Polski](https://github.com/necolas/idiomatic-css/tree/master/translations/pl-PL)
* [Português (Brasil)](https://github.com/necolas/idiomatic-css/tree/master/translations/pt-BR)
* [Русский](https://github.com/necolas/idiomatic-css/tree/master/translations/ru-RU)
* [Srpski](https://github.com/necolas/idiomatic-css/tree/master/translations/sr-SR)
* [Türkçe](https://github.com/necolas/idiomatic-css/tree/master/translations/tr-TR)
* [正體中文](https://github.com/necolas/idiomatic-css/tree/master/translations/zh-TW)
* [简体中文](https://github.com/necolas/idiomatic-css/tree/master/translations/zh-CN)


<a name="acknowledgements"></a>
## Acknowledgements

Thanks to everyone who has provided translations and to all those who
contributed to [idiomatic.js](https://github.com/rwldrn/idiomatic.js). It was a
source of inspiration, quotations, and guidelines.


<a name="license"></a>
## License

_Principles of writing consistent, idiomatic CSS_ by Nicolas Gallagher is
licensed under the [Creative Commons Attribution 3.0 Unported
License](http://creativecommons.org/licenses/by/3.0/). This applies to all
documents and translations in this repository.

Based on a work at
[github.com/necolas/idiomatic-css](https://github.com/necolas/idiomatic-css).
