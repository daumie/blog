---
layout: post
title: Binary Conversions
date:   2016-07-21 18:50:39  
categories: other
---

In this section of the Binary Tutorial we will look at how to easily convert between binary, decimal, hexadecimal and octal numbers.

It's important to be able to translate a value from one number system into another. We need to be able to tell when two values represent the same amount. Sometimes, shortcuts become available to us. For instance octal and hexadecimal are often used as shorthand for binary (we'll see why below). Certain systems will only accept values in a certain base as well. Fortunately, switching between number systems is not too difficult.

## Octal to Binary

Converting from octal to binary is as easy as converting from binary to octal. Simply look up each octal digit to obtain the equivalent group of three binary digits. 

|**Octal-**	|**->Binary**	|
|:---:|:---:|
|  1	|	000 |
|  2	|	001 |
|  3 	|	011 |
|  4	|	100 |
|  5	|	101 |
|  6	|	110 |
|  7	|	111	|
 
**Octal** = 345
**Binary** = 011 100 101 = 011100101 binary

## Hexadecimal and Octal to Decimal

If you need to convert between decimal and hexadecimal or octal it is possible using the methods listed for binary but replacing 2 with either 16 or 8. It will work but if you're like me you're not too good when it comes to your 16 times tables. A better approach is to use binary as a go between. It is easy to convert hexadecimal or octal to binary and then not too hard to go from binary to decimal.

It's a little bit more working but 2 easy steps is generally much better than 1 hard step.


**Example:** 345 Octal to Decimal

345 octal = (3 * 8 <sup>2</sup>) + (4 * 8 <sup>1</sup>) + (5 * 8 <sup>0</sup>) = (3 * 64) + (4 * 8) + (5 * 1) = 229 decimal