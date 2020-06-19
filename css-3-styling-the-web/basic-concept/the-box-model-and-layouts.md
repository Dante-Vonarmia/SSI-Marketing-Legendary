# The box model and Layouts

## What is a CSS Box Model?

## Describe `float`s and how they work.

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

## How many ways to make an elements's position is center to its parent elements?

## Give a sample of align-center. \(Both block and inline elements\)

## Give a sample of vertical align center. \(Both block and inline elements\)

## What's the difference between `margin` and `padding`?

## Explain `margin` collapse?

## `position: static` VS `position: relative` \(hint: DOM flow\)

## What unit when use sizing item?

## What are the common properties to size item, for example min or max size.

## The different between flex-box and grid-box.How to size CSS boxes?

## Name all the properties of the flex-box that you know.

## How to control overflowing content?

## How to control the part of a CSS box that the background is drawn under?

## How do I define inline, block, and inline-block?

## How to create fancy boxes \(also see the Styling boxes module, generally\).?

## How to use background-clip to control how much of the box your background image covers.?

## How to change the box model completely using box-sizing?

## How to add shadows to boxes?

## Using CSS flexible boxes

## Using CSS multi-column layouts

## Using CSS generated content



