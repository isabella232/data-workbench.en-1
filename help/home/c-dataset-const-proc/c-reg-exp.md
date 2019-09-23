---
description: Regular expressions are used across all data workbench search fields including the query entity panels.
seo-description: Regular expressions are used across all data workbench search fields including the query entity panels.
seo-title: Regular Expressions
solution: Analytics
title: Regular Expressions
topic: Data workbench
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
---

# Regular Expressions{#regular-expressions}

Regular expressions are used across all data workbench search fields including the query entity panels.

* [About Regular Expressions](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0) 
* [Regular Expression Terminology](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c) 
* [About Literal Matching](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0) 
* [Using Metacharacters](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2) 
* [Pattern Extraction](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## About Regular Expressions {#section-cc9dc7293bb04fc0b41fe8acdee708f0}

A regular expression is a text pattern, consisting of a combination of alphanumeric characters and special characters known as metacharacters, that locates patterns and extract substrings from text. Regular expressions are widely used in computer programming and are an integral part of languages such as Perl.

To identify and extract complex string patterns, the data workbench server uses regular expressions in some of the transformations and conditions. What follows is a brief guide to regular expressions.

This appendix is not a comprehensive introduction to regular expressions. A particularly good reference is the O'Reilly publication *Mastering Regular Expressions, 2nd Edition* by Jeffrey E. F. Friedl.

## Regular Expression Terminology {#section-80b0d54f731e448391532ab3eb3c525c}

|  Term  | Definition  |
|---|---|
|  Literal  | A literal is a character we use in a regular expression to locate a specific sequence of characters. For example, to find product in [!DNL shop/products.html], the string product is a literal, or what we are literally looking for in the string.  |
|  Metacharacter  | A metacharacter is a special character that has a unique interpretation in the context of regular expressions. For example, the period (.) is a metacharacter that is used to match any character.  |
|  Escape Sequence  | An escape sequence is simply a way to tell the regular expression engine that we would like to use one of the metacharacters as a literal. Escape sequences always start with the backslash character (\). By placing the backslash (which is also a metacharacter) in front of a metacharacter, the regular expression engine interprets the escaped metacharacter as a literal. For example, if you want to match the metacharacter period (.), you need to use an escape sequence. However, to match one of the periods in the string 168.196.0.11, you could use the regular expression consisting of a backslash and a period (\.).  |
|  Pattern  | This is shorthand terminology for the regular expression. In essence, a regular expression is a pattern you are trying to match against the target string.  |
|  Target String  | This term refers to the string we are searching within to locate the desired pattern.  |

## About Literal Matching {#section-ec4497e3160c47ba9b828d939761b3e0}

Literal matching takes a literal string without any escape characters and looks in the target string to see if it is a substring of the target string.

In this example, you see how literal matching works. Consider a situation in which data is collected from website traffic, and the cs(referrer) field contains the following value:

[!DNL http://www.abc.com/adventurenews/today.html?ad=123AZ45]

To determine whether the referrer represents someone who clicked on one of the advertisements, you need to see whether the referrer contains the string ad. You could simply use the literal string ad to search the target string and determine if an advertisement was used to route the traffic to the site. While this would match the target string, it would match in two locations and is thus ambiguous and can lead to false positives.

The following URL contains the string ad in two different places:

[!DNL http://www.abc.com/ad vertnews/today.html?ad =123AZ45]

Thus, if you are trying to determine which sessions started as a result of a particular advertisement campaign, simply using the literal ad as the regular expression is clearly not sufficient. Changing the literal to "ad=" would eliminate this ambiguity and result in the expression making only a single match. However, even this may not be sufficient to ensure that the referrer was part of the advertisement campaign. Consider the following referrer:

[!DNL http://www.xyz.com/hello.html?pad=something]

You do not have any control over the URLs that others may be using to create links to the site. Literal matching is too simple a mechanism to locate sessions that started as a result of the advertisement campaign. The following section discusses how you can use metacharacters for more flexible and powerful matching.

## Using Metacharacters {#section-e29a804336304ea1ba33d40d60139aa2}

A metacharacter is a special character in a program or data field that provides information about other characters. 

|  metacharacter  | description  |
|---|---|
|  . (dot)  | Matches a single character, for example: [!DNL re:x.z] matches "xyz" or "xxz".  |
|  &#42; (star)  | Matches one or more characters, for example: [!DNL re:Z*] matches "ZZZ".  |
|  ? (wildcard)  | Matches 0 or 1 of previous expression to force minimal matching, for example: [!DNL xy?z] matches "xy" and "xyz".  |

Additional common regular expressions can also be used to create more complex search strings.

**Lists, Ranges, and OR**

Literal matching lets you look for a single string, but brackets, dashes, and pipes let you define a list of things to look for in the target string.

<table id="table_18B86955EC3748079E7C176273ADE92B"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> For this metacharacter... </th> 
   <th colname="col2" class="entry"> The regular expression processor will... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> Square Brackets ([ ]) </td> 
   <td colname="col2"> Match any of the characters inside of the bracket with a single character position. For example, [AB] is an instruction to match either the letter A or the letter B and [0123456789] says match to any character in the range 0 to 9. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Dash (-) </td> 
   <td colname="col2"> <p>Match a range of characters. Thus, instead of writing [0123456789] we could simply write [0-9]. </p> <p> This can be extended to ranges of characters and multiple ranges within one set of brackets. For example, [0-9A-C] matches the characters 0 through 9 and A to C. </p> <p> <p>Note:  To test for a dash (-) as a literal inside the brackets, it must come first or last. For example, [-0-9] tests for - and 0 to 9. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Pipe (|) </td> 
   <td colname="col2"> Match one of two choices to a given target string. For example, b|nat matches either bat or nat. </td> 
  </tr> 
 </tbody> 
</table>

Consider the following examples: 

|  Pattern  | String  | Match  |
|---|---|---|
|  Win9[58]  | OS=Win95  | Win95  |
|  Win95|8  | OS=Win98  | Win98  |
|  [0-9]  | Mozilla/3.0  | 3  |
|  Lesson[A-Z]  | Lesson a  | No match because lower-cased a is not in the range of upper-cased A through Z.  |

**Negation**

Negation is a way to say that you would like to match anything except the given characters. The negation metacharacter, the circumflex or caret (^), is used as the first character inside brackets to say that you would like the match to be anything but the remaining characters in the brackets. For example, to match any character but a semicolon (;), you would write

[^;]

This would match any character except the semicolon.

** Positioning**

To force a match to the beginning or end of a target string, one of two metacharacters are used. 

|  For this metacharacter...  | The regular expression processor will...  |
|---|---|
|  Circumflex or Caret (^)  | Match against the beginning of the string. For example, ^[Tt]he would match the target string "The Beginning" but would not match "This is the beginning."  |
|  Dollar sign ($)  | Match against the end of the string. For example, [Ee]nd$ would match "This is the end" but would not match "The end is a special time."  |

>[!NOTE]
>
>When the regular expression contains ^ at the beginning and $ at the end, the entire target string must match the regular expression.

**Matching Anything**

The period (.) is a special metacharacter that matches any character in the target string. For example, the regular expression ^…$ matches any target string that is exactly three characters long. The regular expression "…" matches any target string that contains at least three characters.

**Repeated Patterns**

Iteration metacharacters let you match a pattern more than once. 

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD"> 
 <thead> 
  <tr valign="top"> 
   <th colname="col1" class="entry"> For this metacharacter... </th> 
   <th colname="col2" class="entry"> The regular expression processor will... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> Question Mark (?) </td> 
   <td colname="col2"> Match no instances or one instance of the character immediately preceding the metacharacter (?). For example, the pattern rea?d matches red and read. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Asterisk (*) </td> 
   <td colname="col2"> Match zero or more occurrences of the character immediately preceding the metacharacter (*). For example, the pattern [0-9]* matches any number of the characters 0 through 9 (any integer). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> Plus (+) </td> 
   <td colname="col2"> Match one or more occurrences of the preceding character or range. For example, the pattern thre+ would match three but not through. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> {n} </td> 
   <td colname="col2"> <p>Match the proceeding character or range exactly n times. The following pattern matches United States phone numbers: [0-9]{3}-[0-9]{3}-[0-9]{4}. </p> <p> While not an optimal pattern, it determines whether the target string is in the proper format. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> {n,m} </td> 
   <td colname="col2"> Match the preceding character at least n times and at most m times. For example, fo{1,2}d would match fod and food but not foood. </td> 
  </tr> 
 </tbody> 
</table>

## Pattern Extraction {#section-4389779653b64f6cb7c47615b25c1a79}

Pattern matching is only part of the power of regular expressions. Regular expressions also provide a mechanism for extracting key portions of a target string. This is done through the use of the left and right parentheses. These extractions are typically used as input into another process and are accessed through the use of *%position%*, where position is an integer referring to the count of which set of parentheses was matched.

Consider the following examples of pattern extraction: 

<table id="table_BC8D471B966844049FFFCDEC0F183941"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pattern </th> 
   <th colname="col2" class="entry"> String </th> 
   <th colname="col3" class="entry"> Match </th> 
   <th colname="col4" class="entry"> Extraction </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Win(9[58]) </td> 
   <td colname="col2"> OS=Win95 </td> 
   <td colname="col3"> Win95 </td> 
   <td colname="col4"> %1% = 95 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> (Win)(95|8) </td> 
   <td colname="col2"> OS=Win98 </td> 
   <td colname="col3"> Win98 </td> 
   <td colname="col4"> <p>%1% = Win </p> <p> %2% = 98 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mozilla/([0-9]).([0-9]) </td> 
   <td colname="col2"> Mozilla/3.0 </td> 
   <td colname="col3"> Mozilla/3.03 </td> 
   <td colname="col4"> <p>%1% = 3 </p> <p> %2% = 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lesson([A-Z]) </td> 
   <td colname="col2"> Lesson a </td> 
   <td colname="col3"> No match because lower-cased a is not in the range of upper-cased A through Z </td> 
   <td colname="col4"> </td> 
  </tr> 
 </tbody> 
</table>

