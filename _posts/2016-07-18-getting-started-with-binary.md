---
layout: post
title: Getting started with binary numbers
date:   2016-07-18 08:50:39  
categories: other
---

![Binary](/blog/assets/img/binary.jpg)

# Number Sytems!

## Introduction

A number system is a means of representing amounts of things. Decimal is just one of several number systems though and others, in paticular binary, are important to understand in various fields, especially computing.

---

## Outline

I divided this  Binary tutorial into 3 sections. In general I recommend you work through them in order but if you've come here just to learn about a specific topic then who am I to slow you down, just head straight on over.


1.**Number Systems** - Read on below to discover the theory behind numbers.

2.**Conversions** - How to convert between binary and decimal, hexadecimal and octal.

3.**Arithmetic** - Learn how to perform various arithmetic operations with binary numbers.

4.**Negative Numbers** - Learn how to manage negative numbers in binary 

---

### Patterns and Shortcuts

When you're working with number systems, there are many shortucts you can take to:

- make working with them easier.
- help validate your work / identify silly errors you may have made.

I'll point out some of these as we work through the material but you should always be on the lookout for them yourself (Not just in working with numbers but in other areas too).

In general you want to keep an eye out for patterns, then think about ways you can exploit those patterns for your benefit. With practice you get better at spotting them.

---

### The Decimal System

The decimal number system is the one that we are most familiar with, we use it every day. Decimal is what we refer to as a positional number system. That is, the position of the digits gives meaning to the value they represent. The other number systems _(binary, hexadecimal and octal)_ are also positional, so once we understand the underlying theory of decimal we can easily apply that to understand the other systems.

Let's look at an example:

If I have the number **31415**, what this actually represents is:

`30,000 + 1,000 + 400 + 10 + 5`

Or more precisely

|    |     |     |
|----:|:---:|--------:| 
|3 * 10 <sup>4</sup>|=|	30,000|
|1 * 10 <sup>3</sup>|=|	1,000|
|4 * 10 <sup>2</sup>|=|	400|
|1 * 10 <sup>1</sup>|=|	10|
|5 * 10 <sup>0</sup>|=|	5|

Decimal is **base 10**. This means we have 10 symbols for representing values _( 0 - 9 )_. As we move through each position we multiply that number by 10 to the power of that position (starting at 0 at the far right side)


Decimal is convenient as a number system as every time we increase the power all we need to do is add another 0. For each digit in the number, add the number of 0's required by the position and you've got it's positional value. Then each digit naturally lines up in the overall number.

---

### Binary

**Binary** follows the same pattern as Decimal except that instead of being **base 10**, it is instead base 2. Instead of having 10 symbols to represent values we have two _( 0 and 1 )_.

So Decimal is a base 10 number system, we have 10 symbols and multiply by powers of 10. It follows that Binary is a base 2 number system, we have two symbols and multiply by powers of 2.

Let's look at an example:

If I have the binary number **101010**, this translates into decimal as:

`32 + 0 + 8 + 0 + 2 + 0 = 42`

Or:

1 * 2 <sup>5</sup> =	32
0 * 2 <sup>4</sup> =	0
1 * 2 <sup>3</sup> =	8
0 * 2 <sup>2</sup> =	0
1 * 2 <sup>1</sup> =	2
0 * 2 <sup>0</sup> =	0

As you can see from this example, binary is not as convenient as decimal for humans to read and work with. So you may be asking, Why bother with binary then? The answer is that it is an easier format for computers to work with. It may also be utilised in other areas as a shortcut to represent settings.

- **N/B** Because all powers of 2 except for 0 result in an even number, the only way to get an odd number is to have the right most digit be 1. This may be used as a quick check when doing conversions that you haven't made a silly mistake.

---

### Hexadecimal and Octal

Two other number systems which are commonly used in computing are Hexadecimal and Octal. These are both also base number systems.

- Hexadecimal is base 16
- Octal is base 8

Both of them are closely related to binary. You'll notice that:

- 16 is 24
- 8 is 23

This is not the case with decimal (there is no power of 2 which equals 10). This gives hexadecimal and octal characteristics in relation to binary which decimal does not have. We'll investigate these in the next section, conversions.

For hexadecimal we go up to 15 (remember we start from 0). Once we get to 9 we add the letters of the alphabet A - F to represent 10 - 15 (see the reference table below). 

Let's take the decimal number **27**

In hexadecimal this would be 1B which in decimal translates into:

**1 * 16 <sup>1</sup> + 11 * 16 <sup>0</sup> = 16 + 11**

And in octal it would be 33 which in decimal translates into:

**3 * 8 <sup>1</sup> + 3 * 8 <sup>0</sup> = 24 + 3**

### Prefixes

As you can see with the examples above, the numbers can potentially look the same whether they are binary, decimal, octal or hexadecimal. If I gave you the number 2F7 you would know straight away that it was hexadecimal but if I gave you the number 101 is it:

- 101 in binary and 5 in decimal
- 101 in decimal
- 101 in hexadecimal and 257 in decimal
- 101 in octal and 65 in decimal

??

As you can see, the quantity that 101 represents varies by quite an amount depending on the base we are using. To help avoid this ambiguity we add prefixes to the numbers to identify their base.


- Decimal doesn't have a prefix.
- Hexadecimal has the prefix Ox, eg: Ox1B
- Octal has the prefix O, eg: O421
- Binary has the prefix Ob, eg: Ob1101

Some people use a suffix instead but these are not as popular:

- Decimal doesn't have a suffix.
- Hexadecimal has the suffix H, eg: 1BH
- Octal has the suffix O, eg: 421O
- Binary has the suffix B, eg: 1101B

Note: for the prefixes and suffixes above it is a capital o not a zero.

For most of this tutorial I won't use the prefixes but identify the base directly to make it clearer.

### Referance Table

Here is a reference table for the different number systems. It is useful for converting between binary and hexadecimal or octal _(and vice versa)_.

|Decimal 	|Binary 	|Octal 	|Hexadecimal|
|:---|---:|---:|---:|
|0 	|0000 	|0 	|0|
|1 	|0001 	|1 	|1|
|2 	|0010 	|2 	|2|
|3 	|0011 	|3 	|3|
|4 	|0100 	|4 	|4|
|5 	|0101 	|5 	|5|
|6 	|0110 	|6 	|6|
|7 	|0111 	|7 	|7|
|8 	|1000 	|10 |8|
|9 	|1001 	|11 |9|
|10 |1010 	|12 |A|
|11 |1011 	|13 |B|
|12 |1100 	|14 |C|
|13 |1101 	|15 |D|
|14 |1110 	|16 |E|
|15 |1111 	|17 |F|

**N/B** You'll notice that there is a pattern to the binary. The far right column alternates between 0 and one. The next column does the same but 2 at a time. The third column does the same but 4 at a time. The far left column does the same but 8 at a time. This pattern makes it easy to verify it's been written correctly.

f you are doing an exam on binary you often aren't allowed to take material in but nothing is stopping you drawing this table out yourself after the exam has started. It can be a good reference , especially for conversions which we'll look at in the next section.

### Advice

This stuff can be a little hard to get your head around. If you find reading through the material doing your head in a bit here's what I suggest:

- Work through examples on paper. Learning binary is kinda like riding a bike. The best way is just to do it.
- Leave it a day or two then come back and have another go.
