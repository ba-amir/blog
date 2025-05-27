+++
title = "Thirteen Reasons to Love Perl"
date = "2025-05-18T22:15:34+01:00"
#dateFormat = "2006-01-02" # This value can be configured for per-post date formatting
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["Perl", "Programming Languages"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
draft = true
+++

## Introduction

Perl has to be one of the most fun programming languages ever invented. Its 
wide litany of quirks range from mildly interesting to batshit insane and I mean
that in the best way possible. In recent years, pretty much anything 2010 upwards, 
Perl has been much maligned as being "dead" or "write once everywhere" but none 
of that matters here because Perl is honestly really really fun to play around with.
Listed below are thirteen reasons why you should love Perl and if none of them 
manage to, at the very least, make you raise an eyebrow then I'm sorry but we can't 
be friends anymore. 
(too much? kinda reads like a YouTube script)

Also Disclaimer, keep in mind that Perl was designed to be a **scripting** language 
so while some of the features listed below would demerits in other contexts,
with Perl they just play into its philosophy of imposing the least of amount of 
limits in the program and of course TIMTOWDI (There Is More Than Way To Do It)

## 1. Sigils!!! 

Sigils are most likely the first thing you'd notice about a Perl program and 
they probably contribute, in no small part, to Perl's reputation of being difficult to 
parse. But they're actually really important. For one thing, sigils separate Perl 
variables from Perl keywords and functions, this reduces ambiguity so you don't have 
to worry about your variables clashing with already existing functions, we say they are 
in separate namespaces. 
```perl 
my $say = "Hello, World!"; # we declare local variables in Perl using `my`
say $say # we can have functions with the same names as variables without clashes. 
```

But that's not all, Sigils are also handy for indicating the data type of a variable. 
You should note that Perl has only three fundamental data types: Scalars, Arrays and 
Hashes. You're probably full of questions right now- what do your mean only three data types? 
and what about integers and strings and such? We'll get back to the second question in the 
next section about context.

Perl's Data Types 

1. Scalar 
    uses the `$` sigil (kinda looks like an s), a variable containing singular value could either be a number or a string.
2. Array 
    uses the `@` sigil (kinda looks like an a), a variable contaning a to a plural value. Note that there's a subtle difference 
    between lists and arrays in Perl. Lists are the sequence while Arrays are the varables containing them. This sounds like pedantry
    but the use will become more apparent later on.
3. Hashes
    uses the `%` sigil (kinda looks like an h), associates a key to a value. correspond to dictionaries or Maps from other programming languages. 

So not only do sigils give variables a separate namespace for variables, they also give each type of data a separate variable namespace. 
so `$num` and `@num` are entirely different variables. Which is useful when you have repitive names. 

```perl

my @num = 1,2,3,4,5;
my $num 

```
I also find it rather interesting that Sigil's were somewhat inspired by the use of plural suffixes in natural languages. 

Another really cool thing about suffixes is that they aid variable interpolation, take a gander at the example below. 

```perl
my $name = "non-discreet stranger"; 
say "my name is $name"
```

without any special syntax. Sigils make string interpolation really convenient, try it out with hashes and arrays. 

## 2. Context Matters

Just like in natural languages where the meaning of a statement depends heavily on statement. The same is 
true for Perl but slightly less so. Rememeber how in the earlier section we talked about Perl having 
only three data types this possible because whether it's a string or a numeric value depends on 
context.  (TODO: write this again please)

```perl 
my $n = 25; 
my $s = 25 . "0"; # $s is a string
my $n2 = 25 + 2   # $n2 is a number

```

(TODO: give a useful example where it saves casting overhead)

(TODO: talk about how Perl's numeric and string operators do not overlap preventing ambiguity)

(TODO: assigning an array to a scalar does....)
```perl

my @nums = 1,2,3,4,5; 
my $average = sum(@nums)/@nums

```

The above works because `/` is a numeric operator. It expects a number so `@nums`
acts as a number in this context 

3. Regex Everwhere
    - smart match
4. Default variables
    - $_ 
    - @_ 
5. Statement Modifiers
    - unless 
    - if 
    - until
6. Blocks and Higher Order Functions
7. Non-integer indexes
9. CPAN 
10. Optional Parenthesis is Function calls
11. Optional Argument Lists
12. You already have it
13. Community
14. Quotes
1
