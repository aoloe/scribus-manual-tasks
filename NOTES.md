# Notes

## Text formatting

### Paragraph borders

In Scribus you cannot define paragraph borders.

Of course, you can set a border for the frame, but you will then have to break the text frame in multiple linked frames.

There is a workaround for adding horizontal lines inside of a text frame: to define a right aligned tabulator with the "underscore" as the fill character.  
You should define it in a new style that you will apply to the paragraph before the one where you want to see the top line.  
If you want a bottom line, you will add it on the following line.

## Images

### Centering images

There is one thing Scribus can't do: aligning images inside of a frame.

But what it can do is:

- Make the frame the same size/shape as the image: `Right-click > Adjust Frame to Image`.
- Align the image frame relative to other frames or against the Page by using `Windows > Align & Distribute` palette.

## Pages

### Définition fond de page

scribus ne permet pas de définir une couleur imprimée sur toute la page. les bons designers achètent du papier de la bonne couleur!  
scribus supporte ce workflow en te permettant de définir la couleur de font dans les propriétés du document!  
cette couleur ne sera pas imprimée.

et si tu veux vraiment vider ton toner, tu peux toujours mettre un rectangle de la bonne couleur dans le gabarit (ou dans un calque en arrière plan d'une page spécifique)

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

if you know LaTeX, you can also use a render frame to create your table.

a better tables engine is in the working... but i'm not sure it will be really usable before the next stable release will be out.

## When using tables

if you want my feedback as a reader: avoid tables in you document.  
avoid showing raw numbers, and if you have to, use tabulators.

if your layout does not fit in a tabulators setup, it's likely that the result will be over complicated and a pain to read for most readers.

and, of course, there are documents that need  complex tables, but most would be better without them.

## PDF output

### Making text selectable

Depending on how how the text is laydout on the page and what formatting he has used, scribus will not place the text as a stream on the page, but as individual (group of) glyphs.

There are tools like Ghostscript, PDF viewers, or other tools to make the text better selectable.

Scribus is a dtp tool made for printing on proffessional presses and distributing the pdf on the internet is considered (only) a side product... (and the PDF format has also been created for printing and is not the optimal format for distributing content on the web... but, of course, you cannot always choose perfection :-)

## Syntax highliting for code

### Load highlighted code into a text frame

- Generate the highlighted code in html form
  - Some text editors can do that, otherwise (from Vim you can use the `:TOhtml` command to create an html version of the higlighted file: You can open it with Libreoffice but not with Scribus)
  - Paste your code in an online service (like <https://tohtml.com/>)
  - Copy the rendered text
- Paste the highlighted text into a Libreoffice Writer document
- Save the .odt file
- Load the .odt file in a text frame in Scribus.

### Use the render frames with Latex

Lars Behrens on january 6, 2017 in the scribus mailing list

- Prerequisites: Of course you need LaTeX installed, plus the "listings"-package which may or may not be in your default LaTeX installation, depending on your environment.
- In Scribus insert a render frame (shortcut "D")
- Right-click on the frame and choose "Edit Source"
- On the "Fonts/Headers" tab insert the following in the "Additional Headers" text field on the right:
~~~
\usepackage{listings}
\usepackage{color}
\lstset{ %
backgroundcolor=\color{white},  % choose the background color
basicstyle=\footnotesize,       % size of fonts used for the code
breaklines=true,               % automatic line breaking only whitespace
captionpos=b,                   % sets the caption-position to bottom
commentstyle=\color{green},     % comment style
escapeinside={\%*}{*)},      % if you want to add LaTeX within your code
keywordstyle=\color{blue},      % keyword style
stringstyle=\color{red},        % string literal style
}
~~~

  The variables in the lastset section define how your source code examples will be displayed, find details in the mentioned doc file "listings.pdf".
- Remove the example text in the code field on the left
- Now you can insert your code examples in the text field on the left.  
  Make sure that you choose the right language in the "[language=XXX]" tag. A short example in Java:

~~~~
\section{Java}
\begin{lstlisting}[language=java]
class HelloWorldApp {
    public static void main(String[] args) {
        System.out.println("Hello World!"); // Display the string.
        for (int i = 0; i < 100; ++i) {
            System.out.println(i);
        }
    }
}
\end{lstlisting}
~~~

As you can see, basically you just have to surround your code example with

~~~
\begin{lstlisting}[language=YourLanguage]

\end{lstlisting}
~~~

- by clicking the "Update" button at the bottom of the render frame dialog you can check if your code is rendered correctly
- make sure to click "Ok" when your done inserting your example code, otherwise your input might get lost
- you can edit your code at any time by right clicking the render frame again and clicking "Edit Source"
- if you need more render frames just copy an existing one and edit it, so that you won't have to go through the process of inserting the header lines again.

