# Performance & SEO

## What will happened if you don't add DOCTYPE for HTML5

The foremost thing that you need to make sure is that have you added the DOCTYPE in your HTML file.

Doctype basically helps your browser to recognize in which language is your website’s code written. If you don’t specify that, some of the smart browsers will understand it themselves but some dumb browser will not be able to figure out what happened, and they will render some element of your website in a way that you would not like.

So, if you want that IE6 and above should imitate the behavior of browser like chrome and Firefox you may want to add a `strict doctype`.

```markup
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN""http://www.w3.org/TR/html4/strict.dtd">
```

If you don’t do that, the browser will work in `Quirks mode` and will emulate the behavior of older versions.

## What is the advantage of collapsing white space?

It is always good habits to follow a clean code guide not only for yourself, but also for the whole team and future developer.

A proper collapsing white space will make your HTML structure tree simply easier to read and more reasonable. It's a basic routine to always check your own HTML structure trees.

## Common cross browser compatibility issues.

#### Find cross browser compatibility issues with Opera Mini Mobile Browser:

If you are using elements like

* CSS3 3D Transforms
* 2D transforms
* Background image
* HTML5 form features
* Semantic elements
* Placeholder-shown CSS pseudo-class
* Web Authentication API
* Theme-color Meta Tag

etc then your website will fail to perform on Opera Mini browsers.

### With Firefox Browser:

Firefox usually supports the most latest technologies. Mozilla is a trend setter in web tech. However, there are still some elements that Firefox browsers do not support fully such as:

* Filesystem & FileWriter API
* Web SQL Database
* XHTML+SMIL animation
* EOT fonts

### With Safari

Shared Web Workers,CSS overflow-anchor, Web Authentication API, if used will not work at all in safari browsers. However, safari partially supports some of the features like HTML5 form features, CSS Masks. So these features if used may also lead your website to not work properly in Safari browsers.

### Use Separate Stylesheets For Different Browsers

This will save you from a heck of stylesheet problem. You can link to different stylesheet for every browser using conditional comments. So that Chrome will render chrome’s stylesheet, Firefox will go for its stylesheet and so on.

The basic conditional comment will look something like this:

```markup
<!-- [if IE ]>
    <link href="iecss.css" rel="stylesheet" type="text/css">
<![endif]-->
```

Or you can try that.

```markup
<!-- [If IE]>
    <link type="text/css" href="IEHacks.css" />
 <![endif]-->
 <!-- [if !IE]>
    <link type="text/css" href="NonIEHacks.css" />
 <![endif]-->
```

{% hint style="info" %}
[w3 validator](http://validator.w3.org/) is the only tool you need to validate HTML of your website
{% endhint %}

## Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?

**Placing `<link>`s in the `<head>`**

Putting `<link>`s in the head is part of proper specification in building an optimized website. When a page first loads, HTML and CSS are being parsed simultaneously; HTML creates the DOM \(Document Object Model\) and CSS creates the CSSOM \(CSS Object Model\). Both are needed to create the visuals in a website, allowing for a quick "first meaningful paint" timing. This progressive rendering is a category optimization sites are measured in their performance scores. Putting stylesheets near the bottom of the document is what prohibits progressive rendering in many browsers. Some browsers block rendering to avoid having to repaint elements of the page if their styles change. The user is then stuck viewing a blank white page. Other times there can be flashes of unstyled content \(FOUC\), which can shows a webpage with no styling applied.

**Placing `<script>`s just before `</body>`**

`<script>`s block HTML parsing while they are being downloaded and executed. Placing the scripts at the bottom will allow the HTML to be parsed and displayed to the user first.

An exception for positioning of `<script>`s at the bottom is when your script contains `document.write()`, but these days it's not a good practice to use `document.write()`. Also, placing `<script>`s at the bottom means that the browser cannot start downloading the scripts until the entire document is parsed. This ensures your code that needs to manipulate DOM elements will not throw and error and halt the entire script. If you need to put `<script>` in the `<head>`, use the `defer` attribute, which will achieve the same effect of downloading and running the script only after the HTML is parsed.

## What is progressive rendering?

Progressive rendering is the name given to techniques used to improve the performance of a webpage \(in particular, improve perceived load time\) to render content for display as quickly as possible.

It used to be much more prevalent in the days before broadband internet but it is still used in modern development as mobile data connections are becoming increasingly popular \(and unreliable\)!

Examples of such techniques:

* Lazy loading of images - Images on the page are not loaded all at once. JavaScript will be used to load an image when the user scrolls into the part of the page that displays the image.
* Prioritizing visible content \(or above-the-fold rendering\) - Include only the minimum CSS/content/scripts necessary for the amount of page that would be rendered in the users browser first to display as quickly as possible, you can then use deferred scripts or listen for the `DOMContentLoaded`/`load` event to load in other resources and content.
* Async HTML fragments - Flushing parts of the HTML to the browser as the page is constructed on the back end. More details on the technique can be found [here](http://www.ebaytechblog.com/2014/12/08/async-fragments-rediscovering-progressive-html-rendering-with-marko/).

## Have you used different HTML templating languages before?

Yes, Pug \(formerly Jade\), ERB, Slim, Handlebars, Jinja, Liquid, just to name a few. In my opinion, they are more or less the same and provide similar functionality of escaping content and helpful filters for manipulating the data to be displayed. Most templating engines will also allow you to inject your own filters in the event you need custom processing before display.

## SEO in HTML

Please [follow this page](https://9elements.com/seo-cheat-sheet/).

