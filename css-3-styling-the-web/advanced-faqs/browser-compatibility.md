# Browser Compatibility

## What do the -moz-\*, -ms-\*, -webkit-\*, -o-\* and -khtml-\* properties do?

## How to check and supporting older browsers?

## **How to debugging CSS? What kind of tools do you use?**

## How to debug CSS in the browser?

## Have you ever worked with retina graphics? If so, when and what techniques did you use?

_Retina_ is just a marketing term to refer to high resolution screens with a pixel ratio bigger than 1. The key thing to know is that using a pixel ratio means these displays are emulating a lower resolution screen in order to show elements with the same size. Nowadays we consider all mobile devices _retina_ defacto displays.

Browsers by default render DOM elements according to the device resolution, except for images.

In order to have crisp, good-looking graphics that make the best of retina displays we need to use high resolution images whenever possible. However using always the highest resolution images will have an impact on performance as more bytes will need to be sent over the wire.

To overcome this problem, we can use responsive images, as specified in HTML5. It requires making available different resolution files of the same image to the browser and let it decide which image is best, using the html attribute `srcset` and optionally `sizes`, for instance:

```text
<div responsive-background-image>
  <img
    src="/images/test-1600.jpg"
    sizes="
      (min-width: 768px) 50vw,
      (min-width: 1024px) 66vw,
      100vw"
    srcset="
      /images/test-400.jpg   400w,
      /images/test-800.jpg   800w,
      /images/test-1200.jpg 1200w
    "
  />
</div>
```

It is important to note that browsers which don't support HTML5's `srcset` \(i.e. IE11\) will ignore it and use `src` instead. If we really need to support IE11 and we want to provide this feature for performance reasons, we can use a JavaScript polyfill, e.g. Picturefill \(link in the references\).

For icons, I would also opt to use SVGs and icon fonts where possible, as they render very crisply regardless of resolution.

## How do you serve your pages for feature-constrained browsers? What techniques/processes do you use?

* Graceful degradation - The practice of building an application for modern browsers while ensuring it remains functional in older browsers.
* Progressive enhancement - The practice of building an application for a base level of user experience, but adding functional enhancements when a browser supports it.
* Use [caniuse.com](https://caniuse.com/) to check for feature support.
* Autoprefixer for automatic vendor prefix insertion.
* Feature detection using [Modernizr](https://modernizr.com/).
* Use CSS Feature queries [@support](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports)

## How would you approach fixing browser-specific styling issues?

* After identifying the issue and the offending browser, use a separate style sheet that only loads when that specific browser is being used. This technique requires server-side rendering though.
* Use libraries like Bootstrap that already handles these styling issues for you.
* Use `autoprefixer` to automatically add vendor prefixes to your code.
* Use Reset CSS or Normalize.css.
* If you're using Postcss \(or a similar transpiling library\), there may be plugins which allow you to opt in for using modern CSS syntax \(and even W3C proposals\) that will transform those sections of your code into corresponding safe code that will work in the targets you've used.

