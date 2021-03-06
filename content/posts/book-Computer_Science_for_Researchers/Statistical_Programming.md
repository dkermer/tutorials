### Programming

Most researchers will never be required to create their own functions or use traditional programming techniques. But, it is useful to know what it is possible, so you can learn more about them when it would be useful. 

With data, we use the word "variable" to refer to characteristics of our observation. However, that word can also freqeu



- Variable
- Function: All statistical software has built-in functions or commands, but you can create your own. 
- Loop: A loop is sometimes used in

For example, if you have a list of covariates, you can store them as the word "covariates" and then never have to write the whole list again. 

A big difference between data-focused and general languages is the use of loops. Researchers may need to loop through files in a directory, or a list of dependent variables, both of which can be done without actually lopping through apply functions (R) or list comprehension (Python). But, there will never be a need to loop through the rows of a dataset. 

https://towardsdatascience.com/10-not-so-intuitive-things-about-programming-with-r-a4d9d120c42c

https://blog.revolutionanalytics.com/2015/06/why-has-r-been-so-successful.html

https://www.computerworld.com/article/2497319/business-intelligence-beginner-s-guide-to-r-syntax-quirks-you-ll-want-to-know.html

https://codeandculture.wordpress.com/2010/08/06/some-ways-stata-is-an-unusual-language/





## Automation

Programming is about being able to automate actions. 

1. Make something happen
2. Save the written instructions to record and more easily re-run
3. Compile those instructions into a script file to easily re-run
4. Create a master file to run multiple scripts and redo everything











|        | Language Type                                                | Storage                          | Function         | Iteration          | Script File |
| ------ | ------------------------------------------------------------ | -------------------------------- | ---------------- | ------------------ | ----------- |
| SPSS   | Procedural                                                   | `!macro`                         | `!macro`         | LOOP, DO IF        | syntax file |
| STATA  | Procedural                                                   | ``local_macro'` /`$global_macro` | `program`        | foreach, forvalues | do file     |
| SAS    | [Procedural](http://support.sas.com/documentation/cdl/en/stsstat/62258/HTML/default/viewer.htm#statintro_sect5.htm) | `&macro_variable`                | `!macro_program` | DO                 | program     |
| R      | [Functional](https://adv-r.hadley.nz/fp.html)                | `object`                         | `function`       |                    |             |
| Python | Object-Oriented                                              | `variable`                       | `function`       |                    | script      |

### Functions vs Commands

Function-based vs command-based langauges

There is disagreement over whether the syntax most people use with their statistical software are programming languges. 

Just like when learning a language, knowing the words is not good enough--indeed, that is what dictionaries can do. It is important to understand the grammar, how the words fit together. For example, as a consultant, it is useful for me to be able to say "Use the collapse command" or "add the detail option" h