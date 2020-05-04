---
title: "What Beginning Researchers need to know about Text Files and Markup"
date: 2020-04-20T21:34:54-04:00
draft: true
tags: ["Fundamentals", "Data"]
---



tldr:

- Digital Researchers need to understand the different types of files they work with. 
- Many people make use of Markdown languages without understanding that they are just a part of the Markup ecosystem. 
- The escape character <kbd>\\</kbd> switches a langage interpreter between interpreting characters as text and as a special character. 
- Many researchers do not have a programming background and may not be familiar with some concepts. 

<!--more-->

In general, there are three main types of text files, based on how the text is interpreted.  There is no specific taxonomy and some people use their own scheme. 

- **Plain Text** - No interpretation, inteded to be read exactly as created, though some people utilize symbols to facilitate reading, it is not intended to be interpreted. Typically ASCII-compatible. 
- **Scripts** - This contains the code for a programming language. 
- **Markup** - Extra characters utilize a standard scheme that is interpreted by software as structure, annotation, or display instructions. Some people distinguish between three types of markup: presentational, proceedural, and descriptive. For researchers, there are really just two that matter:
  - **Documents** - Provides instructions regarding the display of text.  
  - **Data** -  Provides structure to the data elements, either text or numeric. 

### Text Files and Version Control 

One of the advantages of text files is that they work really well with version control systems. Although an entire binary file can be saved into a version control system, with text files it can save room by only saving the differences between files, and it will show your changes each time.

### Introduction to HTML, XML, and XHTML

This family of markup languages are used both for documents (HTML) and data (XML). It is easy to identify them by format since they all use **tags** surrounded by <>'s. 

```
<img> </img>
```

For instance, to get the little key icons, I tpe `<kbd>Ctrl</kbd>`  makes  <kbd>Ctrl</kbd>

**H**TML (**H**yper**t**ext **M**arkup **L**anguage) was built to control the display of documents on the internet (hypertext by definition is text that links to other information) and has a defined set of tags for that purpose.. **X**ML (e**X**tensible **M**arkup **L**anguage) is extensible, which means that it can use any set of tags. There are several types used for different reasons. **XH**TML (e**X**tensible **H**yper**t**ext **M**arkup **L**anguage) is like HTML but based on XML instead of SGML, an older and more complex markup language that HTML also came from. See more about these formats in the following sections. 

## Script Files

***Every*** programming script, **including those for statistical software**, is saved in text format. Thus, files of type .sps, .do, .sas, .R, .py, and .sql, can all be opened and written in any [text editor](https://www.computerhope.com/jargon/e/editor.htm).  Although one of the actions may be to print text, the purpose is not to control the display, but to create or process it. 

Programming languages are divided into **interpreted** and **compiled** languages. All statistical software use interpreted languages. Compiled languages like C++ are turned into binary files in order to run. This makes it work much faster because it has already been translated directly into computer instructions and does not need to be interpreted "at runtime" (while it is also following the instructions).  

The advantage of opening the text script file in particular editors are **syntax highlighting **, which refers to the coloring that highlights different aspects of the code, and **code completion**, which helps you remember and type variable and function names. Many text editors used by programmers support highlighting for many languages and allow users to create their own. This has been done for SPSS, Stata, and SAS in programs like Notepad++ and others. 



## Markup - Documents

Text files become more useful when combined with a Markup Language that allows for instructions that display things in a formatted or specialized way. Markup uses human-readable characters to specify that formatting. Some are complex and some are simpler.  But complexity usually allows for much more control over the output. 

### Topics

#### WYSIWYG

Many people today cannot remember a time when computers could only display plain text. To control the look of the document, users would add tags or control codes--essentially markup--to indicate how the document would look once printed.  When computer displays improved and software took advantage of it, visible markup was unnedeed: make words bold on the screen, get words in bold when printed.

>  "**W**hat **Y**ou **S**ee **I**s **W**hat **Y**ou **G**et" -> WYSIWYG ("wizzy-wig") 

Back before programs like Microsoft Word was introduced, word processors could not do much more than text editors today. They did all text formatting had to be added by a type of markup that would appear on the scrre.  When graphical document editors were introduced that would actually display bold text in bold, it was a big deal. 

- Rich Text:	  
- Markdown:   "What You See Is What You Mean" 

refers to "Rich Text" document editors that do not use Markup. You make the text on the screen look how you want (with formatting and spacing) and it will save and print *exactly* how it appears on the screen (there is a continuum of how exactly, of course, but it is that idea). 

Referring to markdown in particular, though it applies to other Markup as well, some people have tried to illustrate the distinction with: 

There are some WYSIWYG-like markdown editors, but the use of markup cannot be ignored. **Rich Text Editors** show the actual formatting, and will convert it to underlying binary or HTML code only as needed. 

#### Converting

- pandoc
- Writage - add-in for Microsoft Word to save as Markdown

### Types

#### HTML

HTML is a specific implmeentation of XML for making webpages. Because it is used to make web pages, many more people are familiar with HTML 

Similarly, HTML files are text, have markup that web browsers use to construct formatted text, tables, and links.  The [.docx format](https://www.toptal.com/xml/an-informal-introduction-to-docx) is also a type of text, though it is complex, spread across multiple files and zipped. Utlilzing xml. Microsoft Word's newest .docx extension is actually a text format (zipped XML), though it has much more extranneous information than RTF files so it is much harder to access the content. Plain text or Markup ill be the best in the long run. 

Tags are <tag>stuff</tag>

Pre-defined tags especially for displaying documents on the internet. You cannot add your own tag. 

```
This is some <strong>bold</strong> text. 
```

#### RTF / Rich Text Format

[Rich Text format](https://en.wikipedia.org/wiki/Rich_Text_Format) (RTF), was the standard text-based alternative to Microsoft Word's binary document format for many years and is thus supported by many document editing programs. Most people these days will use a simpler options like Markdown, but RTF is still used by many programs. For example, some statistical output will save to RTF instead of Word format (some actually save in RTF but say it is Word to avoid confusion!). For your purposes, they can be treated as the same. 

Here is an example of RTF from Wikipedia: 

```
{\rtf1\ansi{\fonttbl\f0\fswiss Helvetica;}\f0\pard
This is some {\b bold} text.
}
```

which simply displays this: 

> This is some **bold** text.

#### TeX / LaTeX 

LaTeX ("lah-tech", though some say "lay-tex") is the oldest and most-used academic markup scheme, having been released in 1984. It provided a more user-friendly way of using TeX, which actually implements the styling which was intended to allow writing papers with complex mathematical expressions. LaTeX helps to set up the document. 

R Markdown/Knitr uses some parts of LaTeX to produce the nicely formatted pdf documents (thus, either MiKTeX or TinyTeX must be installed on Windows computers). 

```
\documentclass{article}
\begin{document}
This is some \textbf{bold} text. 
\end{document}
```

It is similar to RTF in that there are many \\'s and {}'s, but notice that the brackets here are after the 

#### Markdown

Markdown is a general term for minimal-markup document structures. For example, putting astrisks around a word to add emphasis. Just like ASCII, there is a [basic implementation](https://www.markdownguide.org/cheat-sheet/) that all the others use. The different  markdowns are called "[flavors](https://github.com/commonmark/commonmark-spec/wiki/markdown-flavors)", and include RMarkdown and GitHub Flavored Markdown (GFM) .



There are tons and tons of different styles that people have made. For instance, in a Markdown text document (a specific style of Markup), surrounding a word with asterisks will make it display in italics. 

```
This is some **bold** text. 
```

[Comparison of Markdown and HTML](https://www.markdownguide.org/basic-syntax/)

## Markup - Data

### Issues

**Basic descriptive statistics** will quickly reveal if a text data file is not interpreted correctly. Values will end up in the wrong column and/or cases maybe split across rows. If you see errors, look at the entire row of data (specifically, columns to the left) to identify where the problem started. 

### Types

#### Delimited

To delimit something means to mark the boundaries of something. In delimited data files, the column boundaries are marked (e.g., sepearated) with a character.  Any character can be used, but the most common **delimiters** are: 

| Delimiter | Character                                         | Extension        | Notes                                                        |
| --------- | ------------------------------------------------- | ---------------- | ------------------------------------------------------------ |
| Comma     | <kbd>,</kbd>                                      | .csv             | Most computers will automatically open in Excel              |
| Tab       | <kbd>Tab</kbd><br /> <kbd>\\</kbd>+<kbd>t</kbd>   | .tab, .tsv, .txt | Less common in text, so fewer conflicts. But, can be difficult to identify. |
| Pipe      | <kbd>\|</kbd><br /><kbd>Shift</kbd>+<kbd>\\</kbd> | .dat<br />.txt   | Rarely used in text and looks like a column break. But, must be specified, and thus much harder for others to use. |

Specifying the **text qualifier** (usually double quotes) may also be necessary. It is needed if the data itself contains line breaks (\n) or the delimiter, so the data in that field will be surrounded by the text qualifier. If the data has both commas and quotes, then software should *escape* (put a backslash before) any quotes in the data for you (but not always) . 

#### Fixed Format

Fixed format files look like big blocks of numbers and **do not have variable names** in the first row. Back when hard drive space was precious, it was common for data to be stored that way because there was no need for delimiters which were non-data characters that took up room. Instead, each column was allocated a specific number of characters and thus could be identified by position. The label ASCII does not itself specify fixed format (delimited data can also be encoded as ASCII), but is often listed as such because it is an older file. To read this type of file, it is necessary to have a separate "setup file" for a statistical software to know which data to put in which column. 

#### JSON

When data **is not tabular**, JSON can be used. They are much more versitille as they allow for nested columns. The data can also be in any order and does not need to include missing values.  JSON is preferred because the markup is simpler (fewer characters), leading to smaller and easier-to-read flies. For strictly tabular data, though, a delimited file would be smaller as the variable/field names do not need to be repeated for each record/row. 

Jupyter Notebok files (.ipynb) are stored in JSON with [specified elements](https://nbformat.readthedocs.io/en/latest/format_description.html). 

#### XML

e**X**tensiible **M**arkup **L**anguage A general type of markup. There are many standards for using it like, TEI is another. For text as data. See [TEI](https://tei-c.org/) . For [Qualitative Data Analysis (old)](http://www.qualitative-research.net/index.php/fqs/article/view/852/1850). 





## Escapes

See also https://www.spss-tutorials.com/escape-sequence/

### Escape Character

In each kind of markup, some characters have special meaning. For example, in Markdown, which I am writing in, surrounding a word with asterisks (*) is the way to make it in *italics*. But, sometimes you actualy want the processor to treat them as regular text. To switch back and forth between special and text, you "escape" the character

If you look back at RTF and LaTeX, you will notice that all the markup starts with the backslash. 

However, if I want the interpreter to treat the asterisks as regular characters and not as instructions, I need to: 

**escape** them putting a backslash in front of the character:  \\\*escape\\* 

Programming languages usually have a way to indicate that you wish to write a **raw string**, one in which all characters are interpreted as plain text. Markup allows for code blocks, which are also treated as a raw string. 

The escape character is actually like a switch, and can turn regular characters into special ones for certain interpreters. In programming languages, when giving instructions to print some text, you can add a tab with \t and a line break with \n.

These sequences, plus many other escape sequences are used in **regular expressions**, which are a way to be very specific when searching for text. 

The backslash is the traditional escape character and is essentially universal. One of  the  annoyances about using Windows compters is that it uses the backslash in **file path names**. So, it is important to use Mac-style forward slashes in file paths with markup or other programming languages. 

To tell the interpreter that the next character has a special meaning. To "escape" from parsing the characters as text, or parsing the characters as code. It's easier to think of it as a "switch" that tells the interpreter to flip between interpreting characters as text to interpreting them as a special character. It goes both ways. For instance, 



[Escaping (especially in SPSS and Python) ](https://www.spss-tutorials.com/escape-sequence/)

### Escape Sequences

The backslash is the universal "escape" character, through there is a few times when quotes are "escaped" with additional quotes (Excel, SPSS). If you are given the instruction to "escape" a character, it means to put a backward slash `\` right before it. 

#### Modifier Keys

It's the same idea as when we hold down the <kbd>Ctrl</kbd>, <kbd>Shift</kbd> or <kbd>Alt</kbd> keys while pressing a letter key. Instead of typing the letter, the computer performs some action.  <kbd>Ctrl</kbd>+<kbd>C</kbd> means to copy the text, not to type the letter "c". Those are called Modifier keys, but it's the same idea.

### Quotes

In syntax, escapes may be needed to include quote marks inside a quoted string. Excel does the same when you must double your double-quotes to have them print

```
="What do you mean by ""Escape""?"
```

#### Windows File Paths

You may have seen that langauges such as R do not understand file paths written in the Windows style. That is because it sees each \ as an escape so it tries to interpret the next letter as having a special meaning.  If you actually want to specify the character `\`, you must escape it `\\` .  However, modern versions of Windows will also accept the Mac/Linux style of file paths using `/`. 



### Escape Sequence Example

Here is an example of using a programming language to print a message:  

```
print "Hello!\nThis is an \"Expert\" Question:\tWhat does \\n mean?"
```

This produces: 

> Hello!
>
> This is an "Expert" Question:	What does \n mean? 

- Notice how the entire message (after the word print) is enclosed in quotes. 
- `\n` is the Line Feed control character, which is typically called a "new line"

- `\t` is a tab, not a "t" 

- `\"` means to interpret `"` as text instead of the default (end of the message)