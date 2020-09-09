---
title: ""
date: 2020-04-20T21:34:54-04:00
draft: true
tags: ["One", "Two"]

---

Description 

<!--more-->

As mentioned earlier, the first 32 codes in ASCII represented non-printing "Control Characters" like Tabs and Spaces. 

In text documents, there are a number of non-visible "control characters" that you need to be aware of. 

### EOLs: CR, LF, and CRLF

For more in this section, see https://blog.codinghorror.com/the-great-newline-schism/ 

There are two codes relating to ending a line of text, which are collectively called **E**nd **o**f **L**ine ("EOL") codes: the  **C**arriage **R**eturn ("CR") and the **L**ine **F**eed ("LF"). The fact that they are different goes way back to the typewriter. 

Unfortuntaely, the different operating systems decided to use different combinations of those for the files on their computers. Windows uses both "CR" and "LF", Macs used "CR", and Unix computers use "LF".  Since OSX, Macs now follow Unix computers and  use "LF". This can sometimes be seen by Windows users who open a file saved in one of the other operating systems and see all the lines running together (no visible line breaks). 

Modern Text-reading software is aware of this situation and most try to compensate for it (including Windows' Notepad since 2018), showing the file properly regardless of which style of line ending. Many programs that deal with sharing files with different types of systems, like the version control software Git, will automatically convert this for you, but this is a setting that can be turned off and there are messages about it. All programmer-focused text editors will also detect and convert line endings easily and/or automaitcally. 

The difference in line endings can especially cause problems with programming languages that rely on line endings, like Stata and Python. 



## File Types



### File Extensions and MIME Types

So, how does a computer know whether to decode the binary values as text or do something else with them? https://www.howtogeek.com/192628/mime-types-explained-why-linux-and-mac-os-x-dont-need-file-extensions/

it is common to put information about the type at the beginning of a file. 

Windows programs instead utilize a "file extension" at the end of the file name to determine what software should open it. Most software can also decode several different types of files, and may use the extension to pick from among them (others will attempt to detect the proper format or look at metadata like Macs). If a user changes the extension without actually converting the contents of the file, it cannot be opened properly. Just like a ASCII/Unicode reader finds gibberish when it tries to read a binary file, only the proper software will be able to decode the file into useful content.  