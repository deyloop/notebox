# Enabling MathJax support on Github pages

Github does have MathJax rendering when rendering math equations from
markdown in its built-in markdown preview, but when the same markdown
with math equations get deployed to Github pages, the math rendering
support is provided by the Jekyll theme instead.

The default Jekyll theme used by Github pages does not support MathJax
rendering out of the box, but it is easy to get it going.

Just create `_includes/head-custom.html` with the following:

```html
 <!-- MathJax -->
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" 
    async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>

<script id="text/javascript">
  window.MathJax = {
   tex: {
     inlineMath: [['$', '$'], ['\\(', '\\)']]
   }
  };
</script>
```

Explaination:

* The content of `_includes/head-custom.html` file is injected into the
  `<head>` of the site that gets generated.
* The first two `script` tags enable MathJax support for all content on
  the rendered site.
* The last script section makes it so that inline math can use `$` to
  demarcate themselves. This is not enabled by default[^1]

[^1]: [20221127122723](../20221127122723/) MathJax: Tex and LaTeX Math delimiters
