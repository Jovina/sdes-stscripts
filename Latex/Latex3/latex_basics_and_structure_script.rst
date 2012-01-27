.. Objectives
.. ----------

.. By the end of this tutorial, you will be able to

.. 1. Understand basic structure of a LaTeX document, its various document
..    classes and loading packages that add new features to the LaTeX system.
.. #. Create a LaTeX document with a title and an abstract.
.. #. Create numbered and non-numbered sections and subsections in a LaTeX
..    document.
.. #. Create an appendix in a LaTeX document.
.. #. Create a table of content in a LaTeX document.

.. Prerequisites
.. -------------

.. 1. latex_intro 

     
.. Author              : Harish Badrinath < harish [at] fossee [dot] in > 
   Internal Reviewer   : 
   External Reviewer   :
   Langauge Reviewer   : 
   Checklist OK?       : <put date stamp here, if OK> 

Script
------

.. L1

{{{ Show the  first slide containing title, name of the production
team along with the logo of MHRD }}}

.. R1

Hello friends and welcome to the tutorial titled "Basics of LaTeX and its 
document structure".

.. L2

{{{ Show the objectives slide }}}

.. R2

.. By the end of this tutorial, you will be able to

.. 1. Understand basic structure of a LaTeX document, its various document
..    classes and loading packages that add new features to the LaTeX system.
.. #. Create a LaTeX document with a title and an abstract.
.. #. Create numbered and non-numbered sections and subsections in a LaTeX
..    document.
.. #. Create an appendix in a LaTeX document.
.. #. Create a table of content in a LaTeX document.

.. L3

{{{ Switch to the pre-requisite slide }}}

.. R3

Before beginning this tutorial,we would suggest having a working installation of
LaTeX and suggest you to complete the tutorial titled "Introduction to LaTeX".

.. L4


.. R4

We begin this tutorial with an example introduced in the previous tutorial.
The text in the document is illustrative and can be replaced replaced by a 
single alpha-numeric character, for example. When done so, the resulting 
document could be described as the shortest possible LaTeX input document, that
creates an output file. It consists of 3 LaTeX commands and one line/character
of text.

In our minimal example, document is an environment. Only the text enclosed by 
the begin and end commands is effected by the environment. The part of the file
before the \begin{document} command is called the preamble, and is used to 
"configure" the LaTeX typesetter and change various parameters for typesetting.
In our current example, the preamble is empty. We will add preamble content
in the later part of the tutorial.
This is processed by a TeX processor that generates an output file. Now, we 
begin to look into each line in the example in more detail.

The first line reads

.. L5


.. R5

which more generally can be written as

.. L6


.. R6

Where documentclass is a LaTeX command.
Parameters specify if you want to use a non default font size, for example.
More specifically the parameters can be used to alter things like font size of 
the document, paper size, two sided or single sided printing, etc, for each
class, that is supported by LaTeX.

The supported classes have a few differences, in how the content of the document is typeset.

.. L7


.. R7

We now look at a hypothetical documentclass command.
The command being shown on the screen, instructs LaTeX to 
Create a new document of class report. The available classes are article, proc,
report, book, slides, letter.
12 pt: sets the font size of main font. Other are relatively adjusted. 10pt is
the default. 
a4paper: specifies the paper size
draft:  marks hyphenation and justification problems in typesetting
with a square in the margin

.. L8


.. R8

This statement can be used optionally and is used to include packages, which are
used to extend the LaTeX's capabilities. There are a number of packages that are
included by default with LaTeX2 base distribution. You can use the texdoc
command for accessing package documentation.

.. L9
::


.. R9

We add the title, the author and the date to the document before the 
\begin{document} directive. We compile the document to see if the details 
appear in the document, but they donot.

.. L10


.. R10

The command \maketitle adds title, authors name and date to the output file.
Of these only the date is optional. If date command is specified, then the given
date is used else today's date is used. 

.. L11


.. R11

The abstract command is used to insert abstract of a document, into the output
file.Place it in the location, where you want your abstract to present in
the document. It is available for the document classes article and report, but
not book

.. L12



.. R12

Titles chapters and sections are used to help the user find his or her way
through your work. The following commands are available in the article class:
section, subsection, subsubsection,  paragraph and sub paragraph. The default
behavior is to use numbered sections. We can use un-numbered sections appending
* to section command. If you want to split your document without influencing the
section or chapter numbering use the part command.


.. L13

.. R13

Longer documents can use report or book class. We can add a new chapter using
the chapter command, provided by the report or book class. After compiling the
file shown in the slide we notice that subsections are not numbered. 

.. L14


.. R14

We can change this behavior with the command setcounter , calling it as shown
in the slide. 

.. L15


.. R15

Appendix can be added to the document using \appendix command. any content after
\appendix will be added to the appendix. In the report or book class, we have to
use \chapter to indicate that the chapters are to be numbered as appendices.

similarly for the article class we have to use the section command to indicate
that sections are to be numbered as appendices.

.. L16


.. R16

Lets add a Table of content to the document. The LaTeX command to add a TOC to a
document is using \tableofcontents command and is placed at the point at which
the table of content is to be placed. 

Now, compile the document and look at the output document. It does not have the table of contents!

We compile our LaTeX file as usual. On the first compilation only the "Contents"
heading appears in the document, but the actual table does not appear. You will
need to compile your document once more, for the actual table to appear in your
document. On the first run, LaTeX has gone through your document and generated
a temporary file (.toc), with the entries that should go into the table of 
contents. These entries are made, when you compile your document for the second
time.

Note that any section/block that has been numbered automatically appears in the
table of contents. It is possible to get un-numbered sections, for instance a
Preface or a Foreword section to appear in the Table of Contents.

.. L17


.. R17

Un-numbered sections are added to TOC using \addcontentsline command.
For example we use the command
\addcontentsline{toc}{section}{Intro}
where "Intro" is the text that you want to appear in the Table of contents.

.. L18

{{{ Show slide with exercise 1 }}}

.. R18

Write a LaTeX script that creates a document of type article, which contains both
a table of content and an appendix. The table of content should be at the 
beginning of the document and the appendix at the end.

The book should contain two chapters, with the first chapter containing two 
numbered and two un-numbered sections. The first un-numbered section should be
present in the table of content.

Please pause the tutorial and check back for a possible solution

.. L19

{{{continue from paused state}}}
{{{ Show slide with solution to exercise 1 }}}

.. R19

This slide on screen shows a possible valid solution to the given exercise.

.. L20

{{{ Show summary slide }}}

.. R20

This brings us to the end of this tutorial. In this tutorial, we have,

.. 1. Gained an understanding of the basic structure of a LaTeX document, its 
..    various document classes and loading packages that add new features to 
..    the LaTeX system.
.. #. Created a LaTeX document with a title and an abstract.
.. #. Created both numbered and non-numbered sections and subsections in a 
..    LaTeX document.
.. #. Created an appendix in a LaTeX document.
.. #. Created a table of content in a LaTeX document.

.. L21

{{{Show self assessment questions slide}}}

.. R21

Here are some self assessment questions for you to solve

 1. Is the LaTeX code given below a valid input file (File compiles successfully
and produces the intended result, that is to produce a book with two chapters 
and an appendix.

 2. subsection command can be placed at any arbitrary level. If they get numbered 
by default using the appropriate setcounter command and secnumdepth parameter,
do they automatically appear in the table of content ??

.. L22

{{{Show self assessment questions slide}}}

.. R22

And the answers,

1. Although the given file looks syntactically valid, the output file is not what
we expected. This is mainly because we are trying to use the section command to
create sections in the appendix, for a document whose type is given as a book.

2. No, the \tableofcontents command normally shows only numbered section
headings, and only down to the level defined by the tocdepth counter.

.. L23

{{{ Show the thankyou slide }}}

.. R23

Hope you have enjoyed this tutorial and found it useful.
Thank you!