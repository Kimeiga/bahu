<img src="bahu-logo.svg" width="200" height="200">

Bahu
====

Literally the smallest amount of css that you would need to get a site running with a **dark theme** and reasonable styling defaults without assuming anything more than that there exists a `<body>`.

Source Code (minified):
-----------------------

_Only 290 bytes!_

    *{max-width:100%}body{margin:2rem auto;max-width:50rem;line-height:1.6;font-size:1.125rem;background:#111;color:#eee;padding:1rem;font-family:sans-serif}h1,h2,h3{line-height:1.2}a{color:tan}pre{white-space:pre-wrap}input:not([type=checkbox]):not([type=radio]),select,textarea{display:block}

No need to import any `npm` module or pull down any `<link>`. Just copy and paste into a `<style>` element in your `<head>`! Now stop worrying about CSS frameworks, responsive design, bundle size, time to first paint, etc. and **focus on coding your web app!**

Find the code on [GitHub](https://github.com/Kimeiga/bahu)!

Source Code (unminified):
-------------------------

    * {
      max-width: 100%;
    }
    
    body {
      margin: 2rem auto;
      max-width: 50rem;
      line-height: 1.6;
      font-size: 1.125rem;
      background: #111;
      color: #eee;
      padding: 1rem;
      font-family: sans-serif;
    }
    
    h1,
    h2,
    h3 {
      line-height: 1.2;
    }
    
    a {
      color: tan;
    }
    
    pre {
      white-space: pre-wrap;
      overflow-wrap: break-word;
    }
    
    input:not([type="checkbox"]):not([type="radio"]),
    select,
    textarea {
      display: block;
    }

* * *

Explanation
-----------

### `* { max-width: 100%; }`

This is to prevent images, figures, forms, and other elements from breaking out of the width of the page.

### `body { max-width: 50rem; }`

This gives the page a readable width of 800px.

### `body { margin: 2rem auto; }`

This is used to center the body on the page.

### `body { font-size: 1.125rem; }`

To give a font size of 18px for the body.

### `a { color: tan; }`

This has to be changed because it defaults to a dark blue that cannot be read on a black background.

The colors that take the least amount of characters to produce in CSS are "red" and "tan", at 3 characters. I liked the look of tan better, so I chose tan for the links color. It shows nicely on the dark background.

[An example.](#)

### `pre { white-space: pre-wrap; overflow-wrap: break-word; }`

`pre` had to be modified so that you could read pre-formatted text that is wider than the viewport. The consensus seems to be to allow it to wrap, so I followed suit. You need both of these declarations for this to avoid expanding beyond the window.

### `input:not([type="checkbox"]):not([type="radio"]), select, textarea { display: block; }` tag

So this is a more complicated one. I basically needed to make the text, date, button, and other inputs display as block so they wouldn't all be inline as this can make html forms into one long line that is rather hard to read. `select`s and `textarea`s are not included in `input` so I just had to add them. However, we don't want checkboxes and radio buttons to push their tags under them as that looks odd, so we exclude them with the `:not` selector.
