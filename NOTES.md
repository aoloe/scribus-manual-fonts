# Notes

## Loading local fonts

When opening a document Scribus will automatically load fonts that are in the same order as the document itself.

It will also look for fonts in the following directories:
- fonts
- Fonts
- Document fonts


This is also valid for IDML files.

p.s.: it will also load color profiles that are in a "profiles/" directory.

p.p.s.: the implementation is in `ScribusMainWindow::loadDoc()`.

## Variable Fonts

Scribus does not support variable fonts.

> Variable fonts are an evolution of the OpenType font specification that enables many different variations of a typeface to be incorporated into a single file, rather than having a separate font file for every width, weight, or style.  
> [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Fonts/Variable_Fonts_Guide); See also [the Wikipedia article on Variable Fonts](https://en.wikipedia.org/wiki/Variable_font)

There is a ticket open in the Scribus bug tracker: [Variable fonts only select one font (the thinnest) per .ttf file](https://bugs.scribus.net/view.php?id=17217).

Sopme thoughts:

- The PDF format does not support variable fonts: so Scribus would need to subset them when exporting to PDF.
- According to the StackOverflow article [Does Freetype support variable fonts?](https://stackoverflow.com/a/64916355/5239250), Freetype seems to support them (only sees a single font).
- Most variable fonts are distributed with a set of "normal" fonts that can be used instead, so support for them is not urgent.
