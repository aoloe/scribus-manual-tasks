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

there is a new tables engine in the working, but -- while being much better -- i don't think that it will be ready for a copy paste from office before the next release.﻿
