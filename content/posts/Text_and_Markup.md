---
title: "Character_Encoding"
date: 2020-04-20T21:34:54-04:00
draft: false
tags: ["Fundamentals", "Data"]
---



tldr:

- 

<!--more-->



### EOL, CR, and LF

For more in this section, see https://blog.codinghorror.com/the-great-newline-schism/ . 

As mentioned earlier, the first 32 codes in ASCII represented non-printing "Control Characters" like Tabs and Spaces. There are two codes relating to ending a line of text, which are collectively called End of Line ("EOL") codes: the  Carriage Return (13, "CR") and the Line Feed (10, "LF"). The fact that they are different goes way back to the typewriter. 

Unfortuntaely, the different operating systems decided to use different combinations of those for the computer. Windows uses both "CR" and "LF", Macs use "CR", and Unix computers use "LF".  This mostly affects Windows users who open a file saved in one of the other operating systems and see all the lines running together (no line breaks at all). 

Text-reading software is aware of this situation and most try to compensate for it, showing the file properly regardless of which style of line ending. Many programs that deal with sharing files with different types of systems, like the version control software Git, will automatically convert this for you, but this is a setting that can be turned off and there are messages about it. All programmer-focused text editors will also detect and convert line endings easily and/or automaitcally. 

The difference in line endings can cause problems espeically with programming languages that rely on line endings, like Stata and Python. 



## File Types



### File Extensions and MIME Types

So, how does a computer know whether to decode the binary values as text or do something else with them? https://www.howtogeek.com/192628/mime-types-explained-why-linux-and-mac-os-x-dont-need-file-extensions/

it is common to put information about the type at the beginning of a file. 

Windows programs instead utilize a "file extension" at the end of the file name to determine what software should open it. Most software can also decode several different types of files, and may use the extension to pick from among them (others will attempt to detect the proper format or look at metadata like Macs). If a user changes the extension without actually converting the contents of the file, it cannot be opened properly. Just like a ASCII/Unicode reader finds gibberish when it tries to read a binary file, only the proper software will be able to decode the file into useful content.  



## Text Data Files

### Delimited

### Fixed Format

## Markup Languages

Text files become more useful when combined with a Markup Language that allows for instructions that display things in a formatted or specialized way. For instance, in a Markdown text document (a specific style of Markup), surrounding a word with asterisks will make it display in bold. 

Markup uses human-readable characters to specify these aspects. It may be complex and hard to interpret by humans who are not familiar with it, though. Wikipedia gives this example of [Rich Text format](https://en.wikipedia.org/wiki/Rich_Text_Format):

> ```
>  {\rtf1\ansi{\fonttbl\f0\fswiss Helvetica;}\f0\pard
>  This is some {\b bold} text.\par
>  }
> ```

which is instructions to display this: 

> This is some **bold** text.

Similarly, HTML files are text, have markup that web browsers use to construct formatted text, tables, and links. 

Other text files, including .R, .do, .py,, .ipynb, and .html are also stored with Markup. 

Microsoft Word's newest .docx extension is actually a text format (zipped XML), though it has much more extranneous information than RTF files so it is much harder to access the content. Plain text or Markup ill be the best in the long run. 

XML, including HTML, Markdown, Textile, LaTeX. 

## Text Data Files

JSON, CSV, TSV.  ASCII does not itself specify fixed format, but fixed format files are often listed as ASCII. 

### Delimited Files

## Escape Characters

Because 

It can be helpful to refer to those Control Characters to be applied at a later time. 

But, if you open a file and the software does not recognize a code, it is most likely to display a question mark in a diamond U+FFFD. �

These "Hex Codes" or "Character Codes" Of course, 4 hexadecimal digits only allow for 

without immediately triggering the action or result. 