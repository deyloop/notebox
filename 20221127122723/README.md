# MathJax: Tex and LaTeX Math delimiters

* <https://docs.mathjax.org/en/latest/input/tex/delimiters.html#tex-delimiters>

MathJax's TeX preprocessor by default uses `\(` and `\)` to delimit
inline math expressions. They do not use `$`. 

The obvious reason is since `$` happens to be a common character that
has meaning in common usage and is regularly used on its own, and any
content that that uses `$` to denote currency for example would have to
now escape it.

This page shows how to change the default delimiters using some
JavaScript

```javascript
window.MathJax = {
  tex: {
    inlineMath: [['$', '$'], ['\\(', '\\)']]
  }
};
```

Notes:

* [20221127114316](../20221127114316/README.md) Enabling MathJax support on Github pages

    #bib
