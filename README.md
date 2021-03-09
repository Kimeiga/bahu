<img src="bahu-logo.svg" width="200" height="200">

# Bahu

Literally the smallest amount of css that you would need to get a site running with a **dark theme** and reasonable styling defaults without assuming anything more than that there exists a `<body>`.


## Source Code (minified):

_Only 209 bytes!_

    *{max-width:100%}body{background:#111;color:#eee;max-width:46em;margin:auto;padding:1em;line-height:2}a{color:tan}pre{overflow-x:auto}input:not([type=checkbox]):not([type=radio]),select,textarea{display:block}

No need to import any `npm` module or pull down any `<link>`. Just copy and paste into a `<style>` element in your `<head>`! Now stop worrying about CSS frameworks, responsive design, bundle size, time to first paint, etc. and **focus on coding your web app!**

Find the code on [GitHub](https://github.com/Kimeiga/bahu)!

## Source Code (unminified):

    * {
      max-width: 100%;
    }

    body {
      background: #111;
      color: #eee;
      max-width: 46em;
      margin: auto;
      padding: 1em;
      line-height: 2;
    }

    a {
      color: tan;
    }

    pre {
      overflow-x: auto;
    }

    input:not([type="checkbox"]):not([type="radio"]),
    select,
    textarea {
      display: block;
    }

## **Even Smaller** Source Code: (minified)

_Only 83 bytes!_

    body{background:#111;color:#eee;max-width:46em;margin:auto;padding:1em}a{color:tan}

I wouldn't recommend using this one because you're missing some things that prevent the page from being wider than the screen, and also some nice styling like line-height. But if you are certain you don't need anything else, I suppose it is fine.

## **Even Smaller** Source Code: (unminified)

    body {
      background: #111;
      color: #eee;
      max-width: 46em;
      margin: auto;
      padding: 1em;
    }

    a {
      color: tan;
    }

## Explanation (of full 209B version)

### `*` tag

#### `max-width: 100%;`

This is to prevent images, figures, forms, and other elements from breaking out of the width of the page.

### `body` tag

#### `background: #111;`

This gives the webpage a dark background.

#### `color: #eee;`

This makes the text off-white to be legible on the dark backdrop.

#### `max-width: 46em;`

This gives the page a readable width.

`em` unit of measure is used to save 1 character over `rem` while still increasing in size with increasing viewport font-size. Since `body` is unlikely to have a font-size placed on it, and even if it did, it would affect everything anyways (as if placed on the `html` element), this usage of `em` is practically identical to `rem`, so it is ok to save this 1 character.

#### `margin: auto;`

This is used to center the body on the page. `margin: 0 auto;` is equivalent, but uses 2 more characters. Since the body is the maximum height of the page anyways, it is ok to have `margin-top` and `margin-bottom` be set to `auto` when we use `margin: auto`.

#### `padding: 1em;`

Gives a padding of 1em around the body so that on mobile (or when in a sufficiently thin window, there is space between the edges of the screen and the copy. `em` is used for similar reasons to its usage in `body`'s `max-width`.

#### `line-height: 2;`

Used to make the text more bearable to read. I considered a fractional unit like "1.5" or "1.7", but to save 2 characters I chose "2". It still is quite a bit more legible than when in it's default state of "1".

### `a` tag

This has to be changed because it defaults to a dark blue that cannot be read on a black background.

#### `color: tan;`

The colors that take the least amount of characters to produce in CSS are "red" and "tan", at 3 characters. I liked the look of tan better, so I chose tan for the links color. It shows nicely on the dark background.

[An example.](#)

### `pre` tag

#### `overflow-x: auto;`

`pre` had to be modified so that you could read pre-formatted text that is wider than the viewport. The consensus seems to be to allow it to overflow with a scroll, so I followed suit.

### `input:not([type="checkbox"]):not([type="radio"]), select, textarea` tag

#### `display: block;`

So this is a more complicated one. I basically needed to make the text, date, button, and other inputs display as block so they wouldn't all be inline as this can make html forms into one long line that is rather hard to read. `select`s and `textarea`s are not included in `input` so I just had to add them. However, we don't want checkboxes and radio buttons to push their tags under them as that looks odd, so we exclude them with the `:not` selector.

> For the record, if you don't like Times New Roman or whatever default serif font that you are rendering this page with, go ahead and add `font-family: sans-serif;` to your body. But I kinda like Times New Roman, and wanted to save bytes, so I'm ok with it.
