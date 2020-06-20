# Project & Methodology

## Why doesn't my CSS, which is valid, render correctly?

## Explain BEM? OOCSS?

## What existing CSS frameworks have you used locally, or in production? How would you change/improve them?

* **Bootstrap** - Slow release cycle. Bootstrap 4 has been in alpha for almost 2 years. Add a spinner button component, as it is widely used.
* **Semantic UI** - Source code structure makes theme customization extremely hard to understand. Its unconventional theming system is a pain to customize. Hardcoded config path within the vendor library. Not well-designed for overriding variables unlike in Bootstrap.
* **Bulma** - A lot of non-semantic and superfluous classes and markup required. Not backward compatible. Upgrading versions breaks the app in subtle manners.

## What are the advantages/disadvantages of using CSS preprocessors?

**Advantages:**

* CSS is made more maintainable.
* Easy to write nested selectors.
* Variables for consistent theming. Can share theme files across different projects.
* Mixins to generate repeated CSS.
* Sass features like loops, lists, and maps can make configuration easier and less verbose.
* Splitting your code into multiple files. CSS files can be split up too but doing so will require an HTTP request to download each CSS file.

**Disadvantages:**

* Requires tools for preprocessing. Re-compilation time can be slow.
* Not writing currently and potentially usable CSS. For example, by using something like [postcss-loader](https://github.com/postcss/postcss-loader) with [webpack](https://webpack.js.org/), you can write potentially future-compatible CSS, allowing you to use things like CSS variables instead of Sass variables. Thus, you're learning new skills that could pay off if/when they become standardized.

## Describe Block Formatting Context \(BFC\) and how it works.

A Block Formatting Context \(BFC\) is part of the visual CSS rendering of a web page in which block boxes are laid out. Floats, absolutely positioned elements, `inline-blocks`, `table-cells`, `table-caption`s, and elements with `overflow` other than `visible` \(except when that value has been propagated to the viewport\) establish new block formatting contexts.

Knowing how to establish a block formatting context is important, because without doing so, the containing box will not [contain floated children](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context#Make_float_content_and_alongside_content_the_same_height). This is similar to collapsing margins, but more insidious as you will find entire boxes collapsing in odd ways.

A BFC is an HTML box that satisfies at least one of the following conditions:

* The value of `float` is not `none`.
* The value of `position` is neither `static` nor `relative`.
* The value of `display` is `table-cell`, `table-caption`, `inline-block`, `flex`, or `inline-flex`.
* The value of `overflow` is not `visible`.

In a BFC, each box's left outer edge touches the left edge of the containing block \(for right-to-left formatting, right edges touch\).

Vertical margins between adjacent block-level boxes in a BFC collapse. Read more on [collapsing margins](https://www.sitepoint.com/web-foundations/collapsing-margins/).

## What are the various clearing techniques and which is appropriate for what context?

* Empty `div` method - `<div style="clear:both;"></div>`.
* Clearfix method - Refer to the `.clearfix` class above.
* `overflow: auto` or `overflow: hidden` method - Parent will establish a new block formatting context and expand to contains its floated children.

In large projects, I would write a utility `.clearfix` class and use them in places where I need it. `overflow: hidden` might clip children if the children is taller than the parent and is not very ideal.

## What are the different ways to visually hide content \(and make it available only for screen readers\)?

These techniques are related to accessibility \(a11y\).

* `width: 0; height: 0`. Make the element not take up any space on the screen at all, resulting in not showing it.
* `position: absolute; left: -99999px`. Position it outside of the screen.
* `text-indent: -9999px`. This only works on text within the `block` elements.
* Metadata. For example by using Schema.org, RDF, and JSON-LD.
* WAI-ARIA. A W3C technical specification that specifies how to increase the accessibility of web pages.

Even if WAI-ARIA is the ideal solution, I would go with the `absolute` positioning approach, as it has the least caveats, works for most elements and it's an easy technique.

