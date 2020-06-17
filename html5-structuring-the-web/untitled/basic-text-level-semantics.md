# Basic text-level semantics

## The Div VS the Paragraph element, what's the difference?

## [How to create a list of items with HTML](https://developer.mozilla.org/en-US/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals#Lists)

## [How to stress or emphasize content](https://developer.mozilla.org/en-US/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals#Emphasis_and_importance)

## [How to indicate that text is important](https://developer.mozilla.org/en-US/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals#Emphasis_and_importance)

## [How to display computer code with HTML](https://developer.mozilla.org/en-US/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting#Representing_computer_code)

## [How to annotate images and graphics](https://developer.mozilla.org/en-US/Learn/HTML/Multimedia_and_embedding/Images_in_HTML#Annotating_images_with_figures_and_figure_captions)

## [How to mark abbreviations and make them understandable](https://developer.mozilla.org/en-US/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting#Abbreviations)

## [How to add quotations and citations to web pages](https://developer.mozilla.org/en-US/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting#Quotations)

## [How to define terms with HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Define_terms_with_HTML)

## Describe the difference between `<script>`, `<script async>` and `<script defer>`.

* `<script>` - HTML parsing is blocked, the script is fetched and executed immediately, HTML parsing resumes after the script is executed.
* `<script async>` - The script will be fetched in parallel to HTML parsing and executed as soon as it is available \(potentially before HTML parsing completes\). Use `async` when the script is independent of any other scripts on the page, for example, analytics.
* `<script defer>` - The script will be fetched in parallel to HTML parsing and executed when the page has finished parsing. If there are multiple of them, each deferred script is executed in the order they were encoun­tered in the document. If a script relies on a fully-parsed DOM, the `defer` attribute will be useful in ensuring that the HTML is fully parsed before executing. There's not much difference in putting a normal `<script>` at the end of `<body>`. A deferred script must not contain `document.write`.

{% hint style="info" %}
Note: The `async` and `defer` attrib­utes are ignored for scripts that have no `src` attribute.
{% endhint %}

