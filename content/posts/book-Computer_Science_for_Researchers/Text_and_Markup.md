---

title: "What Researchers need to know about Text Files and Markup"
date: 2020-04-20T21:34:54-04:00
draft: false
tags: ["Fundamentals", "Data"]
---

This series is meant for non-programmer researchers who are beginning to use text-based tools and syntax. 

tldr:

- Digital Researchers need to understand the different types of files they work with. 
- Many people make use of Markdown languages without understanding that they are just a part of the Markup ecosystem. 
- The escape character <kbd>\\</kbd> switches a language interpreter between interpreting characters as text and as a special character. 
- Many researchers do not have a programming background and may not be familiar with some concepts. 

<!--more-->

Many people who use digital research methods in academia do not have a computer science or programming background. But, to understand how to work with data and to take advantage of tools for collaboration and replicability, a certain base level of knowledge is useful. This article is my attempt to explain the minimum knowledge researchers should have about text files and the various types of markup. Although some content is specific to tabular data and statistical software, much is also relevant to those in the digital humanities.  





# Types of Text Files

In general, there are three main types of text files based on how the content is interpreted. There is no standard breakdown, but this is a useful way of classifying files that researchers encounter. 

- **Scripts** - For computer instructions or code. 
- **Documents** - For the display of textual documents for reading.  
- **Data** -  For structured text or numeric data. 

Document and data files typically contain **[markup](https://en.wikipedia.org/wiki/Markup_language)**--characters or sequences of characters that provide information above and beyond the document text or data.  Software can recognize and interpret standardized annotations to control the display or processing of a text file. But, individuals can also add their own markup to notate sections you want to keep working on or data that you still need to find. 



## Script Files

In addition to the classic programming languages like C++, Python, and Java, statistical software also have a textual language that can has the ability to save code in a script.  also have  *Every* computer script, **including those for statistical software**, is saved in text format. Thus, files of type .sps, .do, .sas, .R, .py, and .sql, can all be opened and written in any [text editor](https://www.computerhope.com/jargon/e/editor.htm).  

Programming languages are divided into **interpreted** and **compiled** languages. All statistical software uses interpreted languages. Compiled languages like C++ must be converted ("compiled") into binary files in order to run. This can vastly increase speed because the instructions have already been translated into computer code when it is run. 

- Compiled: must be converted ("compiled") into binary files in order to run
- Interpreted: does not need to be compiled
- Interactive shell: allows a command line 
- **G**raphical **U**ser **I**nterface (GUI, "goo-ee")
- **C**ommand-**L**ine **I**nterface (CLI) - Like text chatting vs email
- **I**ntegrated **D**evelopment **E**nvironment (IDE)

Although most of the code is the same in a script and interactively, there are usually some functionality that is only supported in a Script. For instance, Stata allows you to specify multi-line commands with /// only in a script file, not in the command box. 

Stata, R, and Python also support "interactive "programming. That supports one statement or command at a time and shows the output along with the input. A script file, however, contains just the inputted statements and more directly allows the seqeuence of commands to be re-run and the ouput reproduced. If researchers do not save the commands in a script file (e.g., only in output files), then it is far more difficult to redo the processing and analyses. 

### Editors and IDEs

A text editor is the name for any software that can decode and display text files. Some are very simple, and others have many features that can make it easier to write in certain languages. An **I**ntegrated **D**evelopment **E**nvironment, on the other hand, combines a text editor with other tools a language requires like compiling, debugging, and code running. It is typically optimized for a specific language and allows you to run code and manage entire projects. But, some are able to support multiple lagnuages. 

Advanced text editors, IDEs, and built-in script editors allow for features like syntax highlighting and code completion.

-  **Syntax highlighting **refers to the coloring that highlights different aspects of the code. Many text editors used by programmers support highlighting for many languages and allow users to create their own. Notepad++, for instance, can support all the languages by installing some user-contributed files. 

- **Code completion** helps you remember and type names related to your data or words commonly used in the language. 

  

### Statistical Syntax

- Syntax - The structure of the language (e.g., grammar)
- Code - The words in the language (e.g., vocabulary)
  - Code: instructions for a computer ([Miriam-Webster](https://www.merriam-webster.com/dictionary/code))
  - Coding: to create or edit computer code ([Miriam-Webster](https://www.merriam-webster.com/dictionary/code))
  - Syntax: The way in which linguistic elements are put together to form phrases ([Miriam-Webster](https://www.merriam-webster.com/dictionary/syntax))
- Script - A file holding instructions written using a specific language
- Source [Code] - A file with human-readable instructions
- Program - A script performing a function that does not involve any application other than the language's interpreter. 

Because you cannot have a language without both grammar and vocabulary, it is common to use the terms syntax and code interchangably. 

- Coding: Writing code
- Programming: Writing a complete set of instructions for a computer
- Scripting:  Creating a file with code, instead of performing the same tasks interactively (e.g., automating a process)





- Data Table

  - SPSS and Stata work with the opened/target data file, so it is not necessary to specify this.

- Specific Variables

- Command / Function

  

- Options / Arguments

To truly achieve replicability, you want to do scripting. But, coding is the first step



1. Point-and-Click
2. Saving the code
3. Coding
4. Scripting
5. Programming



- Execute
- Run: 
- Do: Stata's term for run but still show everything in the results window

In reality, these are often used interchabably as well. 

Every software language has a **structure**, like a grammar, which is crucial to understand. Being able to look at someone else's syntax and pick out the important words. For traditional software it is usually the first word or few words. For the programming languages (R & Python), it is important to identify the functions (before parentheses)

The table below shows the syntax in the most used quantitative research software that will produce a Contingency Table comparing the variables `q1` and `q2`, with only n (# of observations), row %, and the results of a χ2 test of independence. Lines in italics apply to multiple tasks. 

| Software            | Syntax Example                                               | Comments                                                     |
| ------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| SPSS                | CROSSTABS  <br />     /TABLES= q1 BY q2    <br />     /STATISTICS=CHISQ     <br />     /CELLS=COUNT ROW. | Primarily a point-and-click software <br />with syntax not designed to be typed. <br />Much shorter if defaults are used. |
| Stata               | tabulate q1 q2, obs row chi2                                 | Well-liked due to inherent brevity <br />and other features that reduce typing. |
| SAS                 | *PROC FREQ data=data;*      <br />   table  q1\*q2  <br />        / NOCOL NOPERCENT CHISQ;<br />*RUN;* | Ignoring elements that facilitate multiple <br />statements, it is also quite brief. Tends to <br />include more output by default than others, <br />which required extra syntax to suppress. |
| R                   | *library( summarytools )*<br />ctable(  data$q1, data$q2, chisq=TRUE  ) | Function-based language that relies<br />heavily on supplemental packages <br />(ex. summarytools) designed for your specific task. |
| Python/<br />Pandas | *import pandas as pd<br />from scipy.stats import chi2_contingency*<br />table = pd.crosstab( data.q1, data.q2 )<br />pd.crosstab( data.q1, data.q2, normalize='index' )<br />c, p, dof, exp = chi2_contingency(table) | Python was not designed for this task <br />and no package yet <br />exists to do so. Indeed, the <br />summarytools R package is currently <br />being converted to Python, but as <br />of this writing does not <br />include the ctable function. |

Whether SPSS, STATA, and SAS are or have a "programming language" is a source of debate. However, they are at least "languages", with vocabularies (words *aka* commands or functions) and grammar (word order *aka* syntax). They each have the basic programming abilities to define non-data "variables", create functions and iterate over a list. But, the language is focused on doing data importing, preparation, analysis, and graphing. 

|        | Storage                               | Function                      | File | Type    |
| ------:| ------------------------------------- | ----------------------------- | ---- | ------- |
| SPSS   | `!macro`                              | `!macro`                      | .sps | syntax  |
| STATA  | ``local_macro'` <br />`$global_macro` | `program`                     | .do  | do file |
| SAS    | `&macro_variable`                     | `!macro_program`              | .sas | program |
| R      | `object`                              | `function()`                  | .R   | script  |
| Python | `variable`                            | `function()`<br />`.method()` | .py  | script  |

|             | Code   File   | Code Prompt | Command End   | Case Sensitive | Code Comment |
| ----------- | ------------- | ----------- | ------------- | -------------- | ------------ |
| **SPSS**    | Syntax File   | n/a         | .             | No             | *            |
| **Stata  ** | Do file       | .           | [line  break] | Yes            | *            |
| **SAS**     | Program       | [line #]    | ;             | No             | *            |
| **R**       | R Script      | > *or* +    | [interpreted] | Yes            | \#           |
| **Python**  | Python Script | > or :      | [line break]  | Yes            | \#           |

