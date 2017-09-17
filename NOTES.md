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
