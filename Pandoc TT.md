---
title: Pandoc: Putting you in Control 
authors:
- Allie Watson
- Jenna Herdman
date: 2014-03-03
reviewers: DIGH5000
layout: default
---

##What is pandoc? 

The word *pan* has an origin in ancient Greek: it means everything, inclusive, *all*.

Pandoc is a useful tool for managing and controlling your documents in a marked down format. By learning specific codes and sequences you can control your computer and preserve documents using only your keyboard. The documents you use with Pandoc will survive the constantly changing faces of fancy word processing programs and the plain text format will always be accessible and readable. You can use Pandoc syntax extensions to transform files into different formats and citation styles. 

Pandoc is like driving a car, but a car where the layers of the machine are peeled back to put every mechanism of the vehicle at your fingertips. 

Pandoc opens up your options and expands your intimate knowledge of your computer and how to manage it. Pandoc, like its etymological origins, can embody *all*.

In this tutorial, we (Allie and Jenna) will walk you through some of the basic functions and uses of Pandoc. We will explain how to install it on your computer, how it relies on marked down text applications, and how you can use it to convert documents, navigate your directories, and introduce you to the many ways Pandoc can be useful for academic writing. While our guide is just an introduction, we hope it will make you more comfortable with Pandoc and enthusiastic to begin exploring its many functions and uses.

**Please Note**: We will be restricting this tutorial to Mac users, for now. Windows uses different commands and is a tutorial for another time.  


##What do we find most useful about pandoc? 

- reformat files using command-line operations. For example, the .epub file that won’t open with any of your computer programs can be reformatted by pandoc into an .rtf file that can be opened by any text editing program.
- use templates to format your academic writing. Instead of formatting for MLA, APA, etc. as you write your papers, you can write in simple markdown format, focusing on content. Input the finished document into Pandoc and the outputted document will be formatted into the required citation style. C’est magnifique! 
- writing in markdown allows you to ‘future proof’ your works because a .md file is the simplest, most easy-to-open format for text. This is important in light of phenomena such as planned obsolescence wherein you may suddenly find that Microsoft has changed the formatting requirements of Word and now all of your .docx files cannot be opened. 
- Using markdown format has many advantages - for example, [David Smith’s personal blog](http://www.davidsmith.name/2014/05/23/markdown-for-the-humanities/ “David Smith’s personal blog) says that markdown forces you to write more  instead of getting distracted by formatting and citations. 

#Software & Setup

##Installation
how to install the tool or other prerequisites for using it
- there are different versions for Mac, Windows and Linux [downloadable here](http://pandoc.org/installing.html “downloadable here”)
- if you want to convert files into PDFs, the LaTeX extension is also required. For Mac users, you can download a [simple version of the program](https://tug.org/mactex/morepackages.html “simple version of the program”)

##Setup

After downloading, go through the regular procedures for installing a program. However, when you have finished, you might have difficulty finding the application for pandoc. This is because there is no graphic user interface in the way most applications we download are presented. It functions within the command-line of your computer. More detailed information can be found [on the pandoc website](http://pandoc.org/getting-started.html “pandoc website”)


For Mac users, you open Pandoc in /Applications/Utilities, then clicking the application called Terminal (or hit cmd+space and type in “terminal”). A small, white window will open. Welcome to your new control hub! 
 

#Using the tool

##Basic controls 

Here are some basic commands for orienting yourself in the terminal. Type them into the terminal and then hit <Enter> :

**pwd** + **enter** -- The terminal will tell you what folder you are in. It should start you off in /Users/'your-user-name'

This will reveal your current directory: for example, when I do this, it shows me: 

/Users/joanne
Jennas-Macbook-Pro: ~ joanne$

*For some reason my computer is registered to my mom’s name. Anyway, irrelevant.*

Say you want to navigate between different directories, which are arranged in a sort of narrowing hierarchy. This is the equivalent of opening the little folder that says Documents from your finder, except on a deeper level, as you can make changes to the documents stored there through Pandoc. 

**ls** then **enter** -- This shows you what files and folders are contained in the folder you are currently in.

**cd ..** -- This will move you "up" one level. For example, if you are currently in your Documents directory (/Users/'your-user-name'/documents) then this command will retreat and move you back into your overall directory  (/Users/'your-user-name)’

**cd folder-name** -- This will move you "down" one level. If you want to return to the documents folder, enter **cd documents** or instead, **cd ..**. 


Type in **ls** then **enter** to see what files are contained in that directory. 

Now that we know these basic commands, let’s use them to alter a document! 

###Creating a new directory (through pandoc!)

First of all, let’s create a test sub-directory to play in. First, open the Documents subdirectory by typing in **cd Documents**. 

Second, create the new directory! Let’s call it testing-pandoc, or anything you like so long as it remains consistent for the next little while. So in Pandoc, type in **mkdir testing-pandoc** . This will create your new folder or directory. 

To open your shiny new directory, we use our normal way to going down a level: **cd testing-pandoc** will do the trick. To make sure, verify you’re in the right directory by putting in **pwd** .

###Converting a file (through pandoc!)

In order to play with converting files, let’s create a test file. Open up an application that will let you use plain text, such as Notepad or TextEdit. I’m using Textedit, and have gone through the Preference to ensure the application will show text in its most basic format. Open up our new directory, testing-pandoc, and create your new file there. Mine is called “testytest1.md”.

Next, let’s make sure we’re in testing-pandoc (by using pwd, remember?). Type in *ls* to see all the files in the directory, and make sure you’ve remembered to save testytest1.md there.

To convert my “testytest1.md” I use this command: 

**pandoc testytest1.md -f markdown -t html -s -o testytest2.html**

This is like saying: dear pandoc, please find this file and convert it *from* (-f) this format (markdown) *to* (-t) this format into a new file with this name (-o). Then you can test that it worked by typing in *ls*, and there should be testytest2.html waiting for you. Then open it by typing in: **open testytest2.html.** 

Here's what you end up with:
![HTML](https://github.com/SAllieW/DecemberUpgrade/blob/master/TestytestHTML.png?raw=true) 

So that’s html. But if you want to turn it into a Word document, then it’s the same route, but with the final product having a docx extension. Let’s try: 

**pandoc testytest1.md -f markdown -t docx -s -o testytest3.docx** 

The result:
![docx](https://github.com/SAllieW/DecemberUpgrade/blob/master/TestytestDocx.png?raw=true)

And there they should be, your .md, .html, and .docx files all sitting in the directory, all created with marked down code and transformed through Pandoc. 

There is also the option to convert into PDF (for which you need MacTeX installed, which you can [do here](http://tug.org/mactex/mactex-download.html “do here”)). This requires a small addition to the command line; "-t latex" means basically, "Hey Pandoc, use this tool called latex for this conversion." So it will look like this: 

**pandoc -t latex testytest1.md -f markdown -t pdf -s -o testytest4.pdf**

So now you’ve had the chance to familiarize with Pandoc and get some experience with the way it can manipulate your files. This is useful if you're switching between computers that have different applications for editing these files, and in easily converting said files between formats but maintaining the internal formatting you desire. 

## Using Pandoc for Academic Writing

A promising way to easily format your academic papers is by using YAML (Yet Another Markup Language). By inserting a YAML metadeta block (a chunk of YAML text that acts as a set of instructions for the text) you can add a title and format the document produced by Pandoc. This will be important for the next section of the tutorial about citations. 

Every block must begin and end with three hyphens (---) to delineate which chunk of text is the YAML block. 

The most basic YAML block looks like this at the beginning of your document:

![SimpleYAML](https://github.com/SAllieW/DecemberUpgrade/blob/master/YAMLsimple.png?raw=true)

When you run it through Pandoc and turn it into, say, a PDF, the title should look like this:

![YAMLPDF](https://github.com/SAllieW/DecemberUpgrade/blob/master/YAMLsimplePDF.png?raw=true)

For a great overview on using YAML blocks, see [Marissa's tutorial](https://github.com/digh5000/student-tutorials/blob/master/Marissa-pandoc%20tutorial.md)

##Citations and Bibliographies

The advantages of using Pandoc as part of your academic workflow are not only streamlining the process by making multiple output forms possible, but also eliminating the need for fiddling with finicky citation formats. This section will cover shortcuts for citations and producing bibliography/works cited pages.

This step of the tutorial requires a citation managing program. This can include commonly used programs such as Zotero, Endnote, or Mendeley. It simply has to be a program that can produce a BibTex file. 

I have exported a citation from a sociology text to a .bib file. The file itself looks like this: ![BourdieuBib](https://github.com/SAllieW/DecemberUpgrade/blob/master/BourdieuBib.png?raw=true)

Save this file into the same file folder as the testytest1.md file that we have been experimenting with. It's important that the BibTex file be in the same folder as the document that you want to put the citation into.

Now, open up the testytest1.md file and lets insert a quotation and a citation. Something like this:  ![quote](https://github.com/SAllieW/DecemberUpgrade/blob/master/InTextCitation.png?raw=true)

The important part of this citation is that what comes after "@" matches the name of the .bib file's title, or what comes after the "article{" in the BibTex reference. In this case, it is the "Bourdieu1983" article title that must be included in the document. This will let Pandoc know where to insert the citation details you want. 

But how will Pandoc know where to get the bibliographic information from? We need to beef up our YAML block with a line that tells Pandoc what the title of the .bib file is and to look for it in the same folder as the souce (-s testytest) file.

So here is what your YAML block looks like with a bibliography line: ![bib](https://github.com/SAllieW/DecemberUpgrade/blob/master/YAMLbib.png?raw=true).

It's also a good idea to add a title for the bibligraphy to appear under, so go ahead and add a "Works Cited" section to the bottom of the document.

Finally, run this line of code through Pandoc (AND PRAY!)

pandoc -t latex -S -s testytest1.md --filter pandoc-citeproc -o testytest6.pdf

This code basically tells Pandoc, "Hey, use latex, be smart about it, the source is testytest1.md, you need to deal with citation tags, and the output will be testytest6.pdf"

If all goes well, you should end up with this:
![final](https://github.com/SAllieW/DecemberUpgrade/blob/master/FinalResult.png?raw=true)
The last line of code on the command line (top left) is what turned the .md file (on the right) into the PDF you can see in the bottom left.

Et voila! Once you have everything in place, with a simple line of code you can transform a document that simply references citations, to a fully functioning document with in-text citations and a works cited page that didn't require you to type any of the information yourself. Ah, technology is a wonderful thing.

#Conclusion

- there are a wide variety of programs that can be used in conjunction with Pandoc because markdown is easily read and converted. For example, Zotero can help users manage and structure documents in larger projects.
- Learning about Pandoc and familiarizing yourself enough to use it as a tool is **tough.** It involves understanding not only the Pandoc commands, but also writing text that is marked down. 
- We suggest that after experimenting with the tool in the ways we’ve explained, you explore how it can be used when switching between citation styles. 

###Further resources 
- [Schmidt: basics of Markdown](http://benschmidt.org/2014/09/05/markdown-historical-writing-and-killer-apps/ “basics of Markdown”)
-  [Tenen and Wythoff: using Pandoc and Markdown for academic papers](http://programminghistorian.org/lessons/sustainable-authorship-in-plain-text-using-pandoc-and-markdown “Tenen and Wythoff”)
-  [Pandoc.org: A less condensed but more comprehensive guide to what we’ve shown you today](http://pandoc.org/getting-started.html)

