# Styling Syntax

## Name new feature modules which are used in CSS3.

## How to style text?

## How to customize a list of elements?

## How to style links?

## How to add shadows to text? \(CSS3\)

## How to write comments in CSS?

## How to specify colors in CSS?

## How would you implement a web design comp that uses non-standard fonts?

Use `@font-face` and define `font-family` for different `font-weight`s.

## How to get different font?

[https://www.lifewire.com/change-fonts-using-css-3464229](https://www.lifewire.com/change-fonts-using-css-3464229)

## How to bold or italic text?

## What are the main properties for styling images.

## Why do we need to styling tables in web page? Any common properties?

## Value units: `px` VS `pt` VS `em` and `rem` etc.

## How to select elements via attribute name and content?

## How to apply multiple selectors to the same rule?

## How do we make a rounded corner by using CSS?

## What's the difference between `inline` and `inline-block`?

I shall throw in a comparison with `block` for good measure.

|  | `block` | `inline-block` | `inline` |
| :--- | :--- | :--- | :--- |
| Size | Fills up the width of its parent container. | Depends on content. | Depends on content. |
| Positioning | Start on a new line and tolerates no HTML elements next to it \(except when you add `float`\) | Flows along with other content and allows other elements beside it. | Flows along with other content and allows other elements beside it. |
| Can specify `width` and `height` | Yes | Yes | No. Will ignore if being set. |
| Can be aligned with `vertical-align` | No | Yes | Yes |
| Margins and paddings | All sides respected. | All sides respected. | Only horizontal sides respected. Vertical sides, if specified, do not affect layout. Vertical space it takes up depends on `line-height`, even though the `border` and `padding` appear visually around the content. |
| Float | - | - | Becomes like a `block` element where you can set vertical margins and paddings. |

## What is the CSS `display` property and can you give a few examples of its use?

* `none`, `block`, `inline`, `inline-block`, `flex`, `grid`, `table`, `table-row`, `table-cell`, `list-item`.

| `display` | Description |
| :--- | :--- |
| `none` | Does not display an element \(the elements no longer affects the layout of the document\). All child element are also no longer displayed. The document is rendered as if the element did not exist in the document tree |
| `block` | The element consumes the whole line in the block direction \(which is usually horizontal\) |
| `inline` | Elements can be laid out beside each other |
| `inline-block` | Similar to `inline`, but allows some `block` properties like setting `width` and `height` |
| `table` | Behaves like the `<table>` element |
| `table-row` | Behaves like the `<tr>` element |
| `table-cell` | Behaves like the `<td>` element |
| `list-item` | Behaves like a `<li>` element which allows it to define `list-style-type` and `list-style-position` |

## What's the difference between a `relative`, `fixed`, `absolute` and `static`ally positioned element?

A positioned element is an element whose computed `position` property is either `relative`, `absolute`, `fixed` or `sticky`.

* `static` - The default position; the element will flow into the page as it normally would. The `top`, `right`, `bottom`, `left` and `z-index` properties do not apply.
* `relative` - The element's position is adjusted relative to itself, without changing layout \(and thus leaving a gap for the element where it would have been had it not been positioned\).
* `absolute` - The element is removed from the flow of the page and positioned at a specified position relative to its closest positioned ancestor if any, or otherwise relative to the initial containing block. Absolutely positioned boxes can have margins, and they do not collapse with any other margins. These elements do not affect the position of other elements.
* `fixed` - The element is removed from the flow of the page and positioned at a specified position relative to the viewport and doesn't move when scrolled.
* `sticky` - Sticky positioning is a hybrid of relative and fixed positioning. The element is treated as `relative` positioned until it crosses a specified threshold, at which point it is treated as `fixed` positioned.

