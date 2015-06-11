# Notes

## Text formatting

### Paragraph borders

In Scribus you cannot define paragraph borders.

Of course, you can set a border for the frame, but you will then have to break the text frame in multiple linked frames.

There is a workaround for adding horizontal lines inside of a text frame: to define a right aligned tabulator with the "underscore" as the fill character.  
You should define it in a new style that you will apply to the paragraph before the one where you want to see the top line.  
If you want a bottom line, you will add it on the following line.

## Tables

### Can you paste tables from RTF or Docx to Scribus?

no, you cannot paste them as tables.  
the scribus tables engine is (still) pretty basic.

but you can load them into scribus as bitmap images or import them as vectors (pure vectors, text should be converted to outlines).

there is a new tables engine in the working, but -- while being much better -- i don't think that it will be ready for a copy paste from office before the next release.

## How to do tables

the scribus tables support is rather basic.

generally speaking, it's better to work with tabulators, as long as you don't need lines around the cells.

if you really want tables in scribus, there is an entry for it in the insert menu and a button in the toolbar.

otherwise, the easiest way of creating a table, is to do create it in libreoffice, export it as an image and load that image (at a big enough resolution, but not huge!) into an image frame.  
an alternative is to export it as a svg (with text converted to path) and import it as vectors into scribus.

a better tables engine is in the working... but i'm not sure it will be really usable before the next stable release will be out.
