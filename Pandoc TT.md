---
Allie and Jenna’s Tool Tutorial for Pandoc
---

#Introduction#

##What is pandoc? 

A useful tool for managing and controlling your documents in a marked down format. By learning specific codes and sequences you can control your computer and preserve documents using only your keyboard. The documents you use with pandoc will survive the constantly changing faces of fancy word processing programs and the plain text format will always be accessible and readable. You can use pandoc syntax extensions to transform files into different formats and citation styles. Pandoc is like driving a car, but where you open up the hood and control each movement at the touch of your fingers, making your brain and your keyboard manipulate the codes which cause each movement to be performed seamlessly.

Note: We will be restricting this tutorial to Mac users, for now.  


##What do we find most useful about pandoc? 

- reformat files using command-line operations. For example, the .epub file that won’t open with any of your computer programs can be reformatted by pandoc into an .rtf file that can be opened by any text editing program.
- use templates to format your academic writing. Instead of formatting for MLA, APA, etc. as you write your papers, you can write in simple markdown format, focusing on content. Input the finished document into Pandoc and the outputted document will be formatted into the required citation style. C’est magnifique! 
- writing in markdown allows you to ‘future proof’ your works because a .md file is the simplest, most easy-to-open format for text. This is important in light of phenomena such as planned obsolescence wherein you suddenly find that Microsoft has changed the formatting requirements o Word and now all of your .docx files are unopenable. 
- Using markdown format has many advantages - for example, [David Smith’s personal blog](http://www.davidsmith.name/2014/05/23/markdown-for-the-humanities/ “David Smith’s personal blog) says that markdown forces you to write more  instead of getting distracted by formatting and citations. 

#Software & Setup

#Installation
how to install the tool or other prerequisites for using it
- there are different versions for Mac, Windows and Linux [downloadable here](http://pandoc.org/installing.html “downloadable here”)
- if you want to convert files into PDFs, the LaTeX extension is also required. For Mac users, you can download a [simple version of the program](https://tug.org/mactex/morepackages.html “simple version of the program”)

##Setup

After downloading, go through the regular procedures for installing a program. However, when you have finished, you might have difficulty finding the application for pandoc. This is because there is no graphic user interface in the way most applications we download are presented. It functions within the command-line of your computer. More detailed information can be found [on the pandoc website](http://pandoc.org/getting-started.html “pandoc website”)

For Mac users, you open pandoc in /Applications/Utilities, then clicking the application called Terminal (or hit cmd+space and type in “terminal”). A small, white window will open. Welcome to your new control hub! 
 

#Using the tool

##Basic controls 

Here are some basic commands for orienting yourself in the terminal. Type them into the terminal and then hit <Enter> :

**pwd** + **enter** -- The terminal will tell you what folder you are in. It should start you off in /Users/'your-user-name'

This will reveal your current directory: for example, when I do this, it shows me: 

/Users/joanne
Jennas-Macbook-Pro: ~ joanne$

*For some reason my computer is registered to my mom’s name. Anyway, irrelevant.*

ls -- This shows you what files and folders are contained in the folder you are currently in.


+- cd .. -- This will move you "up" one level. For example, if you are currently in /Users/'your-user-name'/documents then this command will move you into /Users/'your-user-name'
+- cd [folder-name] -- This will move you "down" one level. If you want to return to the documents folder, enter 'cd documents'. 


Next, say you want to open your Documents sub-directory. This is the equivalent of opening the little folder that says Documents from your finder, expect on a deeper level, where you can make changes through Pandoc. 

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

pandoc testytest1.md -f markdown -t html -s -o testytest2.html

This is like saying: dear pandoc, please find this file and convert it *from* (-f) this format (markdown) *to* (-t) this format into a new file with this name (-o). Then you can test that it worked by typing in *ls*, and there should be testytest2.html waiting for you. Then open it by typing in: *open testytest2.html. 

So that’s html. But if you want to turn it into a Word document, then it’s the same route, but with the final product having a docx extension. Let’s try: 

pandoc testytest1.md -f markdown -t docx -s -o testytest3.docx 

Or PDF (for which you need MacTeX installed, which you can [do here](http://tug.org/mactex/mactex-download.html “do here”): 

pandoc testytest1.md -f markdown -t pdf -s -o testytest4.pdf

So now you’ve had the chance to familiarize with Pandoc and get some experience with the way it can manipulate your files. This is useful if you're switching between computers that have different applications for editing these files, and 

## Using Pandoc for Academic Writing
A promising way to easily format your academic papers is by using YAML (Yet Another Markup Language). By inserting a YAML metadeta block (a chunk of YAML text that acts as a set of instructions for the text) you can format the document produced by Pandoc. 

Every block must begin and end with three hyphens (---) (it can also end with three periods (...)) to delineate which chunk of text is the YAML block. 

Here is a [template](https://pbs.twimg.com/media/CRJhdh3WwAAhnBR.png) from a [website](http://kieranhealy.org/blog/archives/2014/01/23/plain-text/) that explains YAML blocks.

It should look like [this](http://kieranhealy.org/files/misc/pandoc-template-html-output-sample.png) after it is converted from markdown through Pandoc.

Here is [mine](https://pbs.twimg.com/media/CRJhdeZWgAAvPGS.png).

It ends up looking like [this](https://pbs.twimg.com/media/CRJhddjW8AEAoaU.png).

So the idea of YAML is great - that you can input simple formatting commands without using elaborate codes. However, the implementation remains ... unclear.

A simpler, non-YAML metadata block you can use looks like this:

% title

% authour(s) 

% date

When I input [this](https://pbs.twimg.com/media/CRJlog3WwAAJInm.png) .md file into Pandoc and convert to .html, I get [this](https://pbs.twimg.com/media/CRJlog3XAAASCyL.png).

#Conclusion
what the reader now knows about the tool, suggestions on further directions to take the tool, readings (if available) where the tool was used to generate new insights, etc.
- there is a wide variety of programs that can be used in conjunction with Pandoc because markdown is easily read and converted. For example, Zotero can help users manage and structure documents in larger projects.
