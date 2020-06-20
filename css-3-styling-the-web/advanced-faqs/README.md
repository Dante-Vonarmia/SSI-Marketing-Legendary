# Advanced FAQs

> [https://developer.mozilla.org/en-US/docs/Learn/CSS/Howto/CSS\_FAQ](https://developer.mozilla.org/en-US/docs/Learn/CSS/Howto/CSS_FAQ)

## Why don't my style rules work properly?

#### HTML elements hierarchy <a id="HTML_elements_hierarchy"></a>

#### Explicitly re-defined style rule <a id="Explicitly_re-defined_style_rule"></a>

#### Use of a shorthand property <a id="Use_of_a_shorthand_property"></a>

#### Use of the `*` selector <a id="Use_of_the_.2A_selector"></a>

#### Specificity in CSS <a id="Specificity_in_CSS"></a>

## How to define responsive design by using media queries?

## What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?How to use filters in CSS

* **Resetting** - Resetting is meant to strip all default browser styling on elements. For e.g. `margin`s, `padding`s, `font-size`s of all elements are reset to be the same. You will have to redeclare styling for common typographic elements.
* **Normalizing** - Normalizing preserves useful default styles rather than "unstyling" everything. It also corrects bugs for common browser dependencies.

I would choose resetting when I have a very customized or unconventional site design such that I need to do a lot of my own styling and do not need any default styling to be preserved.

## How to use blend modes in CSS

