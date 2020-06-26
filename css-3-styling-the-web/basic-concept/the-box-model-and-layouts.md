# The box model and Layouts

## Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.

The CSS box model describes the rectangular boxes that are generated for elements in the document tree and laid out according to the visual formatting model. Each box has a content area \(e.g. text, an image, etc.\) and optional surrounding `padding`, `border`, and `margin` areas.

The CSS box model is responsible for calculating:

* How much space a block element takes up.
* Whether or not borders and/or margins overlap, or collapse.
* A box's dimensions.

The box model has the following rules:

* The dimensions of a block element are calculated by `width`, `height`, `padding`, `border`s, and `margin`s.
* If no `height` is specified, a block element will be as high as the content it contains, plus `padding` \(unless there are floats, for which see below\).
* If no `width` is specified, a non-floated block element will expand to fit the width of its parent minus `padding`.
* The `height` of an element is calculated by the content's `height`.
* The `width` of an element is calculated by the content's `width`.
* By default, `padding`s and `border`s are not part of the `width` and `height` of an element.

## Describe `float` and how they work.

Float is a CSS positioning property. Floated elements remain a part of the flow of the page, and will affect the positioning of other elements \(e.g. text will flow around floated elements\), unlike `position: absolute` elements, which are removed from the flow of the page.

The CSS `clear` property can be used to be positioned below `left`/`right`/`both` floated elements.

If a parent element contains nothing but floated elements, its height will be collapsed to nothing. It can be fixed by clearing the float after the floated elements in the container but before the close of the container.

The `.clearfix` hack uses a clever CSS [pseudo selector](https://github.com/yangshun/front-end-interview-handbook/blob/master/contents/en/css-questions.md#describe-pseudo-elements-and-discuss-what-they-are-used-for) \(`:after`\) to clear floats. Rather than setting the overflow on the parent, you apply an additional class `clearfix` to it. Then apply this CSS:

```text
.clearfix:after {
  content: ' ';
  visibility: hidden;
  display: block;
  height: 0;
  clear: both;
}
```

Alternatively, give `overflow: auto` or `overflow: hidden` property to the parent element which will establish a new block formatting context inside the children and it will expand to contain its children.

## Describe `z-index` and how stacking context is formed.

The `z-index` property in CSS controls the vertical stacking order of elements that overlap. `z-index` only affects elements that have a `position` value which is not `static`.

Without any `z-index` value, elements stack in the order that they appear in the DOM \(the lowest one down at the same hierarchy level appears on top\). Elements with non-static positioning \(and their children\) will always appear on top of elements with default static positioning, regardless of HTML hierarchy.

A stacking context is an element that contains a set of layers. Within a local stacking context, the `z-index` values of its children are set relative to that element rather than to the document root. Layers outside of that context — i.e. sibling elements of a local stacking context — can't sit between layers within it. If an element B sits on top of element A, a child element of element A, element C, can never be higher than element B even if element C has a higher `z-index` than element B.

Each stacking context is self-contained - after the element's contents are stacked, the whole element is considered in the stacking order of the parent stacking context. A handful of CSS properties trigger a new stacking context, such as `opacity` less than 1, `filter` that is not `none`, and `transform` that is not`none`.

_Note: What exactly qualifies an element to create a stacking context is listed in this long set of_ [_rules_](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context#The_stacking_context)_._

## Have you played around with the new CSS Flexbox or Grid specs?

Yes. Flexbox is mainly meant for 1-dimensional layouts while Grid is meant for 2-dimensional layouts.

Flexbox solves many common problems in CSS, such as vertical centering of elements within a container, sticky footer, etc. Bootstrap and Bulma are based on Flexbox, and it is probably the recommended way to create layouts these days. Have tried Flexbox before but ran into some browser incompatibility issues \(Safari\) in using `flex-grow`, and I had to rewrite my code using `inline-blocks` and math to calculate the widths in percentages, it wasn't a nice experience.

Grid is by far the most intuitive approach for creating grid-based layouts \(it better be!\) but browser support is not wide at the moment.

## How many ways to make an elements's position is center to its parent elements?

#### Text-Align Method**:**

1. Enclose the div that you want to center with a parent element \(commonly known as a wrapper or container\)
2. Set “text-align: center” to parent element
3. Then set the inside div to “display: inline-block”

#### Margin Auto Method:

1. Don’t need a parent element.
2. By simply apply “margin: 0 auto” to our box, as long as we have a defined width.

#### Absolute Positioning Method <a id="absolute-positioning-method"></a>

> This method can cause overlapping of elements if used incorrectly.

1. Set the element’s position property to absolute
2. Apply “left: 50%” to the element
3. Set a margin-left of half of the element’s width

#### Transform/Translate Method <a id="transform-translate-method"></a>

This method is used frequently in responsive design and doesn’t require margins to be defined, like in the absolute positioning method.

#### Flex-box Method

The four steps to centering horizontally and vertically with Flex-box are the following:

1. HTML, body, and parent container need to have a height of 100%
2. Set display to flex on parent container
3. Set align-items to center on parent container
4. Set justify-content to center on parent container

{% hint style="info" %}
I like using this method because it’s both **responsive** and **doesn’t require any margin calculations**.
{% endhint %}

{% embed url="https://www.freecodecamp.org/news/how-to-center-things-with-style-in-css-dc87b7542689/" caption="Check this article for more details" %}

## Give a sample of align-center / Give a sample of vertical align center. \(Both block and inline elements\)

{% embed url="https://css-tricks.com/centering-css-complete-guide/" caption="Check this article for more details" %}

## What's the difference between `margin` and `padding`?

In CSS, the margin is the property by which we can create space around elements. We can even create space to the exterior defined borders.

**In CSS, we have margin property as follows:**

* margin-top
* margin-right
* margin-bottom
* Margin-left

**Margin property has some defined values as shown below.**

* **Auto –** Using this property browser calculates the margin.
* **Length –** It sets the margin values in px,pt,cm etc.
* **% –** It sets the width % of the element.
* **Inherit –** By this property we can inherit the margin property from the parent element.

In CSS, padding is the property by which we can generate space around an element’s content as well as inside any known border.

**CSS padding also has properties like,**

1. Padding-top
2. Padding-right
3. Padding-bottom
4. Padding-left

Negative values are not allowed in padding.  


## Explain `margin` collapse?

The [top](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top) and [bottom](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom) margins of blocks are sometimes combined \(collapsed\) into a single margin whose size is the largest of the individual margins \(or just one of them, if they are equal\), a behavior known as **margin collapsing**. Note that the margins of [floating](https://developer.mozilla.org/en-US/docs/Web/CSS/float) and [absolutely positioned](https://developer.mozilla.org/en-US/docs/Web/CSS/position#absolute) elements never collapse.

Margin collapsing occurs in three basic cases:

#### Adjacent siblings

The margins of adjacent siblings are collapsed \(except when the latter sibling needs to be [cleared](https://developer.mozilla.org/en-US/docs/Web/CSS/clear) past floats\).

#### No content separating parent and descendants

If there is no border, padding, inline part, [block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context) created, or [_clearance_](https://developer.mozilla.org/en-US/docs/Web/CSS/clear) to separate the [`margin-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top) of a block from the [`margin-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top) of one or more of its descendant blocks; or no border, padding, inline content, [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height), [`min-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-height), or [`max-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/max-height) to separate the [`margin-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom) of a block from the [`margin-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom) of one or more of its descendant blocks, then those margins collapse. The collapsed margin ends up outside the parent.

#### Empty blocks

If there is no border, padding, inline content, [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height), or [`min-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-height) to separate a block's [`margin-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top) from its [`margin-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom), then its top and bottom margins collapse.

Some things to note:

* More complex margin collapsing \(of more than two margins\) occurs when the above cases are combined.
* These rules apply even to margins that are zero, so the margin of a descendant ends up outside its parent \(according to the rules above\) whether or not the parent's margin is zero.
* When negative margins are involved, the size of the collapsed margin is the sum of the largest positive margin and the smallest \(most negative\) negative margin.
* When all margins are negative, the size of the collapsed margin is the smallest \(most negative\) margin. This applies to both adjacent elements and nested elements.

## `position: static` VS `position: relative` \(hint: DOM flow\)

## What unit when use sizing item?

## What are the common properties to size item, for example min or max size.

## The different between flex-box and grid-box.How to size CSS boxes?

## Name all the properties of the flex-box that you know.

## How to control overflowing content?

## How to control the part of a CSS box that the background is drawn under?

## How do I define inline, block, and inline-block?

## How to create fancy boxes \(also see the Styling boxes module, generally\).?

## How to use background-clip to control how much of the box your background image covers?

## What does `* { box-sizing: border-box; }` do? What are its advantages?

* By default, elements have `box-sizing: content-box` applied, and only the content size is being accounted for.
* `box-sizing: border-box` changes how the `width` and `height` of elements are being calculated, `border` and `padding` are also being included in the calculation.
* The `height` of an element is now calculated by the content's `height` + vertical `padding` + vertical `border` width.
* The `width` of an element is now calculated by the content's `width` + horizontal `padding` + horizontal `border` width.
* Taking into account `padding`s and `border`s as part of our box model resonates better with how designers actually imagine content in grids.

## How to add shadows to boxes?

## Using CSS flexible boxes

## Using CSS multi-column layouts

## Using CSS generated content



