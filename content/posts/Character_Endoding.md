---
title: "Character Encoding"
date: 2020-04-20T12:34:54-04:00
draft: false
tags: ["Fundamentals", "Data"]
---

tldr:

- Computers process and store everything as **binary**. 
- **Codes** are used to represent one thing (e.g., a character) as something else (e.g., a number)
- **ASCII** and **Unicode** (UTF-8) are two common ways of coding text as numbers. Unicode includes ASCII as well as nearly all other languages known to exist. 
- Both files and variables within data files have **types** that specify how to interpret the binary. 

<!--more-->

This article is meant for those using digital research methods who do not have a background in computer science or programming. It is what I think is the minimum you need to know to understand and avoid common issues. 

## Background

For a deeper but more pictorial introduction to the following topics, see Kahn Academy's [Data & Binary](https://www.khanacademy.org/computing/computer-science/computers-and-internet-code-org/how-computers--work/v/khan-academy-and-codeorg-binary-data) video which discusses why computers use binary, describes the binary number system, and introduces how computers represent text, images, and sounds with numbers. Or, learn about the same topics (plus Hexadecimal) by reading [Binary and data representation](https://www.bbc.co.uk/bitesize/topics/zd2xsbk) from BBC's Bitesize GCSE Lessons. 

### Computers and Binary

Computers store and represent information using electricity in transistors, which can have only two states: **on** and **off**.

#### Binary

It is common to represent those two states in **Binary** as `1` and `0`.  By combining many `1`'s and `0`'s, the **binary number system** can represent larger numbers. For instance `1101` is 13, and `1100 1000` is 200.  Brush up on how the binary number system works [here](https://www.mathsisfun.com/binary-number-system.html). 

Some terminology: 

- [**bit**](https://en.wikipedia.org/wiki/Bit): Each `1` or` 0` is called a "**bit**", from <u>**bi**</u>nary dig<u>**it**</u>.  
- [**byte**](https://en.wikipedia.org/wiki/Byte): A group of **8 bits** together is called a "**byte**", ex. `1100 1000`

Storing 200 (`1100 1000`) takes 1 byte, as it needs 8 bits (binary digits). A byte has 256 different possible values and is a common standard unit of bits. 

The binary number system is only one of many ways to interpret the meaning of bits. But, it is a clear, simple, and mathematically useful way of doing so. 

#### Hexadecimal

Writing binary can get tedious, so it is far more common to write in hexadecimal. **Hexadecimal** is a base-16 system, in which each character can have 16 values (`0`-`9` + `A`-`F`). Thus, 2 hex characters can represent 1 byte (8 bits).  For example, the decimal number 200 is `C8` in hexadecimal (also written `0xC8`).  Brush up on Hexadecimal [here](https://www.mathsisfun.com/hexadecimals.html). 

> `1100 1000` (binary) = C8 (hexadecimal) = 200 (decimal)

#### Codes and Coding

Since computers can only store and process `1`'s and `0`'s, and by extension numbers, how does it do so many things? 

Consider [**Morse Code**](https://en.wikipedia.org/wiki/Morse_code), developed over a century before computers. Messages were sent by using long or short burst of sound or the direction a line leaned. When people agreed on which sequences represented each letter and number (the "code"), they could communicate over long distances. 

There are now standard ways to represent text, images, and video using numbers, so we can share all those things with others using computers. This article will only address the representation of text. See the resources at the beginning of this section to learn more about other data types. 

### Text Encoding Schemes

Like Morse Code, people have worked together to develop standards for how bits and bytes are codes for (represent) text.

#### ASCII

**ASCII** (pronounced "ask-ee") was one of the first text coding schemes to get wide use, and is important because current schemes still use it. Each character was assigned a value from 0 to 127. In binary, that takes 7-bits, and the final bit of the byte was used for error checking. 

The 128 **codes** in ASCII include only the most basic characters in American English. For example, 37 is "%", 65  is "A", and 97 is "a". For the full list, see an [ASCII Conversion Chart](http://web.alfredstate.edu/faculty/weimandn/miscellaneous/ascii/ascii_index.html).  The numbers 0 through 32 are codes for non-printing "[Control Characters](https://en.wikipedia.org/wiki/Control_character)", including obsolete commands like a bell/beep, but also the horizontal tab (9) and the space (32). 

Each **number** also has a code. For example, "0" is 48, "1" is 49, and so on. Those codes are not completely arbitrary. In binary, 49 is `0011 0001`. The last 4 bits (`0001`) is 1, and thus matches the number. The last 4 bits of "A" and "a" are both `0001` as well. 

That **a number can be a character** like any letter *and* encoded as a different number is important. Software must be able to determine whether to interpret `0011 0001` as 49 or "1", or something else entirely.  It is convention to put the *encoded* character representation in quotes, and leave the direct numeric representation bare. 

There were **two problems with ASCII**. First, error checking became unnecessary as computers became more reliable, leaving a whole bit essentially unused. Second, since ASCII only included the base English letters, people who wrote in other languages (or who wanted to properly write certain names), were out of luck. 

#### Extended ASCII

Using the 8th bit allowed values up to 255, so there were 128 more characters that could be encoded. Many people made their own **their own coding schemes**, called "**code pages**". Most just added new characters with values above 127, but some also changed characters below that as well. Code pages were developed for many different languages, but only one could be used in any given document. Thus, it was difficult, if not impossible, to write documents in multiple languages, or in many Asian languages which have more than 256 characters. 

Many documents still in existance used one of these code pages, and you will see references to the as well. The most common English/Latin standards were **[ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1)** and the equivalent **[Windows-1252](https://en.wikipedia.org/wiki/Windows-1252)** (not the same, but close enough). The term ANSI (which stands for American National Standards Institute) is sometimes [incorrectly used](https://en.wikipedia.org/wiki/ANSI_character_set) in place of either or both (given their similarity). The maority of code pages have identifiers with the prefixes [ISO, OEM, or Windows](http://www.iana.org/assignments/character-sets/character-sets.xhtml). 

#### Unicode

**Unicode** was developed in 1991 to be a comprehensive solution ("uni" = "one", "one code"). The organization has assigned a code to each character in all of the world's lanugages. For compatibility, the first 127/256 codes were kept the same as ASCII and ISO-8859-1. It is still relatively recent, having only reached [majority use](https://www.w3.org/International/questions/qa-who-uses-unicode) around 2008. 

Unicode values are written in *hexadecimal* and start with U+. So, "A" is still represented by the number 65, but is written U+0041 (4*16+1=65). The character "1" is still 49, written U+0031. Since the first two hex values are 0, these can be represented in 1 byte just like before.  

Unicode also added 2-byte codes (4 hex digits, 16 bits) which allows a total of 65,536 codes. These include the characters for nearly all *modern* languages as well as many symbols (U+FFFD = � ). But, Unicode continued with [3-byte codes](https://en.wikipedia.org/wiki/Plane_(Unicode)), allowing for archaic languages like cuneiform, Emoji, and specialized symbols (ex. musical notes and playing cards: U+1F0A1= **🂡** ). If you know its code, you can directly type [any character into Microsoft Word](https://support.office.com/en-us/article/insert-ascii-or-unicode-latin-based-symbols-and-characters-d13f58d3-7bcb-44a7-a4d5-972ee12e50e0).

**UTF-8** is the most-used implementation of Unicode in the United States because it allows the 1-byte characters to just take up 1 byte (8 bits). This means the file is *identical* to an ASCII or ISO-8859-1 file if only 1-byte characters are used. UTF-8 still supports all of Unicode, but takes an *extra* byte to indicate the presence of each 2 or 3 byte character. UTF-8 is the standard on the internet because HTML markup consists of only 1-byte characters. 

Another common standard, UTF-16, stores *both* 1- and 2-byte characters in 2 bytes. UTF-16 makes files unnecessarily bigger when almost all characters are Latin/English (2 bytes per character instead of 1), but may be a smaller file if it mostly has characters in other languages (2 bytes per character instead of 3). But, UTF-16 files can only be correctly decoded by software that supports Unicode. You may also see "UCS" implementations (ex. UCS-2) which is also Unicode. 

## Digital Research Methods

### Computers

#### Software

All Unicode/UTF schemes can store and display **any character in any language** with [quite limited exceptions](http://www.unicode.org/standard/unsupported.html) (ex. new languages). It even supports [right-to-left languages](http://unicode.org/faq/bidi.html). You need only check if the software supports Unicode to determine if it will handle your data. 

Of course, whether the software can display **menus and messages** in a language is different. Those require understanding the meaning of the language and must be created individually. You much check the documentation to see exactly what features are provided for each language.

Unicode attempts to keep the characters organized by language, and thus ends up with several different codes for essentially the same character. Further, letters with diacriticals (accents) are sometimes written without them. Consequently, Unicode has established a system of "normalization", which identifies similar characters and can help standardize data by **removing accented characters** (ex. á to a). See the [normalization charts](http://www.unicode.org/charts/normalization/) for each language. Each statistical software has  a function that utilizes this: Stata has [ustrnormalize](https://www.stata.com/manuals/m-5ustrnormalize.pdf), SPSS has [NORMALIZE](https://www.ibm.com/support/knowledgecenter/SSLVMB_23.0.0/spss/base/syn_transformation_expressions_string_functions.html), SAS has [BASECHAR](https://documentation.sas.com/?docsetId=nlsref&docsetTarget=p078j5y1bbc9xfn1scp11kw3nmnt.htm&docsetVersion=9.4&locale=en), R has the [UnidecodeR](https://www.rdocumentation.org/packages/UnidecodeR/versions/0.02) package, and Python has the [Unidecode](https://pypi.org/project/Unidecode/) package. 

#### The Internet

Internet URLs currently can only use ASCII characters natively. In addition, spaces and special characters can cause problems. To address these issues, URLs allow representing characters with a percent sign and their hex code. For example, many people have noticed `%20` in a URL: recall that the decimal code for the space is 32, which is `0x20` in hex. 

### Files

The makers of a software decide whether the files it produces should be saved and interpreted according to ASCII/Unicode rules or not. If so, `11001000` will be "A" and so on. But, that same byte could represent  anything the programmer desires. That leads to the two types of files: 

- **Text files** are intended to be decoded into readable characters using one of the standardized text coding schemes
- **Binary files** are not. The bits or bytes can take on any meaning. 

#### Text File Extensions

Many (many) different types of files are **Text** and can be easily examined in a [text editor](https://www.computerhope.com/jargon/e/editor.htm). Examples include: 

- **Script files:** .R, .py, .bat, .sps, .do, .sas, .sql
- **Data files:** .csv, .tab, .tsv, .por, .json, .xml
- **Document files:** .rtf, .ipynb, .md, .rmd, .html, .log, .tex
- **many others:** .ris, .bib, .eml, .ics

Most of these text files also include symbolic [Markup](https://en.wikipedia.org/wiki/Markup_language) that gives information to its software on how the text is structured or how it should display. When you open the file in a text editor instead of the designated software, you can see and edit the instructions along with the content. 

#### Determining File Type

Operating systems are built to automatically open each file with the intended software, and do not indicate whether a file is Text or Binary. But, it is a useful characteristic to know. **To find out**, try opening the file in a [text editor](https://www.computerhope.com/jargon/e/editor.htm) like Notepad (Windows), TextEdit (Mac), [Notepad++](https://notepad-plus-plus.org/) (Windows), [Atom](https://atom.io/), or even Microsoft Word. When trying to open the file on a Windows computer, you may need to change the dialog box to show "All Files" by choosing that from the drop-down box in the lower right, as seen below. 

![Open File Dialog Box](image-20200427213716938.png)

Once opened in a text editor, it is usually easy to tell if you are seeing the contents of a binary file: there is a lot of gibberish on lines of widely varying size, sometimes interspersed with English instructional words. Although you might also see gibberish if the text editor wrongly decodes a document, this is more rare with modern software and the structure is more consistent. For reference, this is what a small section of a **binary pdf file** looks like when opened in Notepad++ (left) and Notepad (right). 

|![Binary PDF File in Notepad++](image-20200424164857605.png)|![Binary PDF File in Window's Notepad](image-20200424165104280.png)

#### Long-term Preservation

**Text files** are typically preferred for long term storage and preservation of data and documentation because the content can be read in a text editor even if the original software is unavailable. However, even though pdf files are binary, it is a [good preservation format](https://www.loc.gov/preservation/digital/formats/fdd/fdd000318.shtml) because is an open standard and well-supported.  

**Data files** produced by statistical software are typically binary (ex. .sav, .dta, .sas7bdat). Although it is good to preserve the original file because it contains additional metadata, it is best to also save data in a text format. The most common are "[delimited](https://en.wikipedia.org/wiki/Delimiter-separated_values)" files where the columns are separated by a symbol such as a comma, tab, or pipe "|". For example, the file extension .csv refers to **c**omma-**s**eparated **v**alues. SPSS's portable .por file is also in text format as it was meant for data transfer. By default, R will write binary data files, but the functions have an option to use ASCII instead. Because these text formats do not store labels and other data information, be sure to make a codebook and store it with the file. 

#### Decoding Issues 

When opening a file, it is important that the software uses the correct scheme to decode text. Since regular English letters and numbers have the same code in all schemes, there is no issue. But, if a file was encoded in Unicode or one of the Extended ASCII schemes and is decoded as plain ASCII or a different scheme, then characters may appear improperly. 

The most common noticeable error seems to be with single or double **quote marks**. Modern software often inserts "[smart quotes](https://support.office.com/en-us/article/smart-quotes-in-word-702fc92e-b723-4e3d-b2cc-71dedaf2f343)" that have [different opening and closing versions](https://www.cl.cam.ac.uk/~mgk25/ucs/quotes.html). But these characters were only introduced in Unicode and are 2 bytes (total of 3 bites if encoded as UTF-8). So, they will appear as 2 or 3 weird characters if decoded by older software or any system not using Unicode. 

Unicode files also support putting a special character, called a **[byte order mark (BOM)](https://en.wikipedia.org/wiki/Byte_order_mark)**, at the beginning to indicate a file is Unicode and which flavor (some details, like endianness, are not addressed here). It is sometimes not used, in part because it may be [interpreted as a weird character](https://www.johndcook.com/blog/2019/09/07/excel-r-bom/). If you encounter extra initial characters, you may need to specify a different decoding (ex. "UTF-8 BOM"). 

UTF-8 is called **variable-length** because the characters may take up 1 byte, 3 bytes, or 4 bytes. Since characters are not the same as bytes, this could potentially make [ASCII better than UTF-8](https://softwareengineering.stackexchange.com/questions/40063/should-character-encodings-besides-utf-8-and-maybe-utf-16-utf-32-be-deprecated) for string decoding and processing. 

### Variables

Just like each file is either Text or Binary, every variable in statistical software has a **type** (*aka* class or encoding), which specifies whether the stored binary values for that variable are interpreted as numbers or treated as codes for their ASCII/Unicode text characters. 

Here are the terms each software gives to the types: 

| Software                                          | Number                         | Text            |
| ------------------------------------------------- | ------------------------------ | --------------- |
| SPSS                                              | numeric                        | string          |
| Stata                                             | byte, int, long, float, double | str / string    |
| SAS                                               | numeric                        | character       |
| R                                                 | int, num / numeric             | chr / character |
| [Pandas](https://pbpython.com/pandas_dtypes.html) | int64, float64, bool           | object          |

When a software has **multiple number types**, they differ in the number of bytes used and whether it stores decimals or just integers. In Stata, for example, the "byte" type uses 1 byte and will only store integers between -127 and 100 (recall 8 bits has 256 combinations).  The long and float types each use 4 bytes (integers vs decimals respectively), and the double uses 8 bytes. All other data types (ex. date or currency) are based on one of the the number types, with formatting or further interpretation. 

If you try to store a very large number in a type that is **too small,** you will lose information. In Stata, for instance, if you are creating a date-time variable it is crucial that you specify the type as double. By default, Stata uses the float type, which does not have enough bytes to store the time precisely. Like other software, Stata helpfully has a compress command that will optimize variable storage. The command has no downside as it cannot cause data loss. Thus, it should be run after creating many new variables. 

The number (unencoded) representation is **better for data** where possible. As you have seen, the number 123 can be stored in 1 byte, whereas "123" would use 3 bytes (ASCII characters 49 50 51). Further, " 123 " would use 5 bytes (32 49 50 51 32) and not considered as the same value. To remove extra spacing and unseen characters, look for software functions named **trim** and **clean**. 

Just as we surround string values with quotes, to specify an empty string value, type two quotes together `""` with nothing in between. To specify an empty numeric value, use the convention for your software: SPSS `$Sysmis` , Stata `.` , SAS `.` , R `NA` , [Pandas](https://pandas.pydata.org/pandas-docs/dev/user_guide/missing_data.html#missing-data-na) `NaN`

#### Numbers + Text

All statistical software also has a way of combining the advantages of text and numbers for variables with a defined set of values. This is particularly useful for [Ordinal variables](http://homes.chass.utoronto.ca/~josephf/pol242/4LevelsofMeasurement.htm): categorical variables that have a specific natural order. Each value does have a non-numeric meaning, but numbers are important to control ordering. Software will stores these values as a number (or code) and then separately store the coding scheme linking the numbers to specific text. 

**SPSS**, **Stata**, and **SAS** all allow numeric variables to have **labels** for each numeric value. Those labels are displayed in output either alone or alongside the number value. But, for data management and calculation purposes, the variable is treated identically to other numeric variables. Thus, it is necessary to refer to the number value when grouping or recoding and regression dummy coding must be done specifically. 

**R** instead has a special data type called **factor**. Although there is an underlying numeric value, it is relevant only for ordering and regression contrasts; for data management purposes, the value must be referred to using its textual label. Factors are treated appropriately as categorical for statistics and visualizations. **Pandas** in Python has the **category** data type. It is treated much like the Text/object variable type even though it also has an underlying numeric representation. It does *not* automatically treat the variable differently from other objects for analysis, such as by dummy coding. 

Converting text variables into numbers + text means that the text label needs only to be **stored once** and the stored number value is just 1 byte (allows integers up to 255).  This is one of the best ways to increase the speed of your software because it can drastically reduce the amount of information (bytes) that the computer must process and store. This is even more true if you have a many rows, long text labels, or a computer with low memory (RAM). 

#### Codes and Coding

The concept of **Codes** and **Coding** is a huge part of any data work. Just like representing the letter "A" with the number 65, it is common to represent groups with numbers as in the previous section. Those numbers also also referred to as codes.  Words like **en**code, **de**code, and **re**code all refer to this concept, both with files and variables. **Encoding** means to assign or replace something with a code. When we save a file, this is what happens--it turns what we have seen and written into bits. When we encode a variable, we assign each Text value a number and add the Text as labels. **Decoding** means to replace or substitute the code with it's meaning so that we can more easily understand it. When we open a file, it is decoded so that we can read it. When we decode a variable, we turn the labels to numbers back into Text value. This can be useful when combining files with different encoding. **Recoding** means to change the codes that were assigned. This is one of the common tasks with variables to combine or re-order groups. For files, though, changing the way that codes are interpreted is called converting. 

|What|Definition|For Files|For Variables|
| ------ | ----------------------------- | --------------------------- | ---------------------------------------------------------- |
| Encode | replace text with a code | save; turns what we see into bits | assign each text value a number and add the text as labels |
| Decode | replace a code with it's meaning | open; allow us to read it | turn the labels to numbers back into a text value. |
| Recode | change the assigned codes | convert | helps to combine or re-order groups |






## More Reading

- [The Absolute Minimum Every Software Developer Absolutely, Positively Must Know About Unicode and Character Sets (No Excuses!)](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)
- [How Unicode Works: What ever devloper needs to know about strings and 🦄](https://deliciousbrains.com/how-unicode-works/)
