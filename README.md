# nvd-mathematical-formulas
This is plugin for editing mathematical formulas in ckeditor 4.
#Introduction:

This plugin is my expansion for current version of Mathematical Formulas plugin. Toolbar is added for creating mathematical formulas faster. Formulas is rended by MathJax. The toolbar UI is based on CodeCogs and modified by us for rendering TeX formulas supported by MathML.

#Some features expanded:

+ Toolbar in dialog for create math formulas faster:

    Create matrix and equation by UI.
    Insert math symbols easly.
    ...

+ Fix bug not auto preview in firefox.

#Setup:

After basic installing, please add mathJaxLib to config:

mathJaxLib: '//cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.4/MathJax.js?config=TeX-AMS_HTML'

#Additional configuration:

config.mathJaxClass - sets the default class for an element that will be converted into a widget.

#Bug:

Currently, this version is lack of language translation.

#Another informations:

Because this is an expansion of Mathematical Formulas plugin, it is not supported in IE 8.
