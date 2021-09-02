# nvd-mathematical-formulas
This is plugin for editing mathematical formulas in ckeditor 4.
# Introduction:

This plugin is my expansion for current version of Mathematical Formulas plugin. Toolbar is added for creating mathematical formulas faster. Formulas is rended by MathJax. The toolbar UI is based on CodeCogs and modified by us for rendering TeX formulas supported by MathML.

# Some features expanded:

+ Toolbar in dialog for create math formulas faster:

    Create matrix and equation by UI.
    Insert math symbols easly.
    ...

+ Fix bug not auto preview in firefox.

# Setup:

Step 1: After basic installing, please add mathJaxLib to config:
mathJaxLib: '//cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.4/MathJax.js?config=TeX-AMS_HTML'

Step 2: Create new JS file and add these code, that will help you automatically update LaTeX symbol to friendly formular.

export function formatMathemicalFormulas() {
  (function () {
    // console.log("Style MF called!");
    var script = document.createElement("script");
    script.type = "text/javascript";
    script.src = "//cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.4/MathJax.js?config=TeX-AMS_HTML";   // use the location of your MathJax

    var config = 'MathJax.Hub.Config({' +
      'extensions: ["tex2jax.js"],' +
      'jax: ["input/TeX","output/HTML-CSS"]' +
      '});' +
      'MathJax.Hub.Startup.onload();';

    if (window.opera) {
      script.innerHTML = config
    } else {
      script.text = config
    }

    script.addEventListener('load', function () {
      window.MathJax.Hub.Queue(["Typeset", window.MathJax.Hub]);
    })

    document.getElementsByTagName("head")[0].appendChild(script);
  })();
}

Step 3: Call above function in your index file.

# Additional configurations:

config.mathJaxClass - sets the default class for an element that will be converted into a widget.

# Bugs:

Currently, this version is lack of language translation.
Working not correctly if current window have more than 1 CKEditor instance.

# Another informations:

Because this is an expansion of Mathematical Formulas plugin, it is not supported in IE 8.
