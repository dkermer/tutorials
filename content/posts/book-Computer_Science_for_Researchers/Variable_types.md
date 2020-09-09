### Variable Types

Just as each file is either Text or Binary, every variable in statistical software has a **type** (*aka* class or encoding), which specifies whether the stored binary values for that variable are interpreted as numbers or treated as codes for their ASCII/Unicode text characters. 

Here are the terms each software gives to the types: 

| Software                                          | Number Variables               | Text Variables  | Number + Text             |
| ------------------------------------------------- | ------------------------------ | --------------- | ------------------------- |
| SPSS                                              | numeric                        | string          | numeric + label attribute |
| Stata                                             | byte, int, long, float, double | str / string    | byte + value label        |
| SAS                                               | numeric                        | character       | numeric + label format    |
| R                                                 | int, num / numeric             | chr / character | factor                    |
| [Pandas](https://pbpython.com/pandas_dtypes.html) | int64, float64, bool           | object          | category                  |

For software that has **multiple number types**, they differ in the number of bytes used and whether it stores decimals or just integers. In Stata, for example, the "byte" type uses 1 byte and will only store integers between -127 and 100 (recall 8 bits/1 byte has 256 combinations).  The long and float types each use 4 bytes (integers vs decimals respectively), and the double uses 8 bytes (necessary for date-time variables). All other data types in statistical software (ex. date or currency) are based on one of the the number types, with formatting or further interpretation. 

| Stata Type | Size    | Values                            |
| ---------- | ------- | --------------------------------- |
| byte       | 1 byte  | -127 to 100                       |
| long       | 4 bytes | integers                          |
| float      | 4 bytes | decimals                          |
| double     | 8 bytes | large numbers, including datetime |

The number representation is **better for data** where possible. As you have seen, the number 123 can be stored in 1 byte, whereas "123" would use 3 bytes (ASCII characters 49 50 51). 

Recall that the **space** is also a character. Thus, " 123 " would use 5 bytes (32 49 50 51 32) and would not be considered equal to "123". To remove extra spacing and unseen characters, look for software functions named **Trim** and **Clean**. 

When writing code, it is necessary to distinguish textual values from the software command term. Always surround string values with quotes.

To avoid text values being interpreted as a command or other software keyword, it is necessary to **surround string values with quotes**. 

To specify a missing value in a text variable, In SPSS, Stata, and SAS, specify an empty (missing or null) string value by typing two quotes together `""` with nothing in between. 

| Software                                                     | Missing <br />Numeric Value | Missing <br />String Value | Missing > # | Missing < # |
| ------------------------------------------------------------ | --------------------------- | -------------------------- | ----------- | ----------- |
| SPSS                                                         | `$Sysmis`                   | `""`                       | `.`         | `.`         |
| Stata                                                        | `.`                         | `""`                       | `TRUE`      | `FALSE`     |
| SAS                                                          | `.`                         | `""`                       | `FALSE`     | `TRUE`      |
| R                                                            | `NA`                        | `NA`                       | `NA`        | `NA`        |
| [Pandas](https://pandas.pydata.org/pandas-docs/dev/user_guide/missing_data.html#missing-data-na) | `NaN`                       | `NaN`                      | `FALSE`     | `FALSE`     |

To specify an empty numeric value, use the convention for your software.

#### Numbers + Text

All statistical software also has a way of combining the usefulness of text and numbers for variables with a defined set of values. This is particularly important for [Ordinal variables](http://homes.chass.utoronto.ca/~josephf/pol242/4LevelsofMeasurement.htm): categorical variables that have a specific natural order. Each value does have a non-numeric meaning, but numbers are important to control ordering.

Changing text values into numeri is one of the best ways to **increase the speed** of your data analysis because it can drastically reduce the amount of information (bytes) that the computer must process and store. 

Advantages over text variables: 

- the text label needs only to be **stored once** for a variable
- the stored number value is just 1 byte (for up to 255 possible values)
- Allows control over the order of values for Ordinal varaibles

 for you to more easily remember what it means

**SPSS**, **Stata**, and **SAS** all allow numeric variables to have **labels** for each value. Thus, you would assign each possible text value a number and make those text values into labels. Those labels are displayed in output either alone or alongside the number value. But, for data management and calculation purposes, the variable is treated the same as other numeric variables. Thus, it is necessary to refer to the number value when grouping or recoding and ensure it is treated as categorical in analyses.  In Stata and SAS, the label is  named and can be applied to multiple variables. 

**R** has a data type called **factor**. Although there is an underlying numeric value, it is relevant only for ordering and regression contrasts. For data management purposes, the value is  specified using its textual label. Factors are treated appropriately as categorical for statistics and visualizations. 

**Pandas** in **Python** has the **category** data type. It is treated much like the Text/object variable type even though it also has an underlying numeric representation. It treats the variable similar to other objects in analyses (e.g.,you must still dummy code).  

#### Codes and Coding

The concept of **Codes** and **Coding** is a huge part of any data work. Just like representing the letter "A" with the number 65, it is common to represent groups of observations with numbers (as in the previous section). Those numbers also also referred to as codes.  Words like **en**code, **de**code, and **re**code all refer to this, both with files and variables.

| What   | Definition                       | For Files                         | For Variables                                              |
| ------ | -------------------------------- | --------------------------------- | ---------------------------------------------------------- |
| Encode | replace text with a code         | save; turns what we see into bits | assign each text value a number and add the text as labels |
| Decode | replace a code with it's meaning | open; allow us to read it         | turn the labels to numbers back into a text value          |
| Recode | change the assigned codes        | called "convert"                  | combine or re-order groups                                 |
