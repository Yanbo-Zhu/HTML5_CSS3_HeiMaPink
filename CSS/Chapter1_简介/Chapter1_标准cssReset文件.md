[Reboot, Resets, and Reasoning | CSS-Tricks - CSS-Tricks](https://css-tricks.com/reboot-resets-reasoning/)

# The word “reset”

Personally, I think it’s useful to think of all of them under the same umbrella term and just be aware of the philosophical differences. But, Normalize intentionally separates itself:

    <mark>A modern, HTML5-ready alternative to CSS resets</mark>

Sanitize calls itself a CSS library and doesn’t use the word “reset” anywhere except to cite the Meyer reset.

# Old reset css file

the Meyer reset： https://meyerweb.com/eric/tools/css/reset/reset.css

HTML5 Reset： http://html5doctor.com/html-5-reset-stylesheet/

CSS Minimal Reset:  [CSS Reset - CSS Referenz - CSS-Wiki.com](https://www.css-wiki.com/css3/css-reset)

# Normalize.css file

[Normalize.css: Make browsers render all elements more consistently.](https://necolas.github.io/normalize.css/)

[GitHub - necolas/normalize.css: A modern alternative to CSS resets](https://github.com/necolas/normalize.css)

Normalize.css represents the first meaningful shift in spirit for what a CSS reset should do.

# new reset css file

[Vanilla CSS Un-Reset](http://cssreset.com/scripts/vanilla-css-un-reset/).

 [MiniReset.css](https://github.com/jgthms/minireset.css).

 [santize.css](https://jonathantneal.github.io/sanitize.css/)

# Reboot

Reboot doesn’t have its own repo, it’s a part of Bootstrap. Here’s the direct file and the docs.

[bootstrap/_reboot.scss at v4-dev · twbs/bootstrap · GitHub](https://github.com/twbs/bootstrap/blob/v4-dev/scss/_reboot.scss)

[Reboot · Bootstrap](https://getbootstrap.com/docs/4.0/content/reboot/)

<br>

Reboot builds upon Normalize, providing many HTML elements with somewhat opinionated styles using only element selectors. 

Additional styling is done only with classes. For example, we reboot some <table> styles for a simpler baseline and later provide .table, .table-bordered, and more.
