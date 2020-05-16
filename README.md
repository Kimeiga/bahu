Bahu
====

Literally the smallest amount of css that you would need to get a site running with a dark theme and reasonable styling defaults without assuming anything more than that there exists a `<body>`.

Source Code (minified):
-----------------------

_Only 215 bytes!_

```css
html{background:#111;color:#eee}a{color:#ec1}body{max-width:46rem;margin:0 auto;padding:1rem;line-height:1.5}h1,h2,h3,h4,h5,h6{font-family:sans-serif}*{max-width:100%}pre{white-space:pre-wrap;overflow-wrap:anywhere}
```

No need to import any `npm` module or pull down any `<link>`. Just copy and paste into a `<style>` element in your `<head>`! Now stop worrying about CSS frameworks, responsive design, bundle size, time to first paint, etc. and **focus on coding your web app!**

Source Code (unminified):
-------------------------

```css
html {
  background: #111;
  color: #eee;
}

a {
  color: #ec1;
}

body {
  max-width: 46rem;
  margin: 0 auto;
  padding: 1rem;
  line-height: 1.5;
}

h1, h2, h3, h4, h5, h6 {
  font-family: sans-serif;
}

* {
  max-width: 100%;
}

pre {
  white-space: pre-wrap;
  overflow-wrap: anywhere;
}
```

**Even Smaller** Source Code: (minified)
----------------------------------------

_Only 93 bytes!_

```css
html{background:#111;color:#eee}a{color:#ec1}body{max-width:46rem;margin:0 auto;padding:1rem}
```

I wouldn't recommend using this one because you're missing some things that prevent the page from being wider than the screen, and also some nice styling like line-height and sans-serif headings.

**Even Smaller** Source Code: (unminified)
------------------------------------------

```css
html {
  background: #111;
  color: #eee;
}

a {
  color: #ec1;
}

body {
  max-width: 46rem;
  margin: 0 auto;
  padding: 1rem;
}
```
