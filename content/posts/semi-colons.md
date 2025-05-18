+++
title = "On Semicolons"
date = "2025-05-18T22:15:47+01:00"
#dateFormat = "2006-01-02" # This value can be configured for per-post date formatting
author = ""
cover = ""
tags = ["Programming Languages"]
keywords = []
description = "Where I ramble about everybody's favourite punctuation mark"
showFullContent = false
readingTime = false
hideComments = false
+++

## Introduction

If I'm being entirely honest, I only have a vague idea on how to use semicolons in writing; 
I know it has to do with separating stuff, but that's about it. So why exactly, you might be 
wondering, am I writing about semicolons on my personal blog? 

It was a bright summer's day and I was in my darkened room lurking on LinkedIn, as one tends to 
do on days like that, when I came across the most bizarre comment. 

> I prefer languages like Python and Javascript to C because they don't force me to add semicolons 
> to the end of every line. 

Now, of course everybody is entitled to their preferences and you don't have to have the most 
well thought-out thesis on why you prefer something to another but I'm sure we can do better 
than semicolons, especially when comparing languages as disparate as C and Python. But ignoring 
the inanity of the above comment, it does beg a somewhat interesting question. 
What's with all the semicolons? Why do some languages need them and others don't? It'll be easier 
to answer the questions after after looking at what the semicolons actually do. 


##  Statement Terminators

Programs written in imperative programming languages can be considered as essentially a list 
of commands to be executed by the computer. But how does the compiler or interpreter or whatever's 
translating the code to the computer know where one command ends and another begins? 

In spoken languages this is pretty simple, just wait until the speaker finishes talking. For writing, 
you'd look out for a puntuation mark- usually a fullstop or an exclamation mark. Programming languages
do the same thing essentially, they use a textual marker to indicate the end of a statement. Some languages use 
newlines (Python) and others use semicolons (C and Javascript). The last sentence wasn't a typo, Javascript 
actually automatically inserts semicolons after each statement wherever they're missing before interpreting 
the program. 

So then, what's the difference? why choose one over the other? Well, like most things pertaining to 
language design it's really a matter of preference. Using semi-colons allows the programmer more flexibility 
in how they structure their code. For example, the following two C snippets are completely identical 
to the C compiler even if one will earn you a talking to.  

```C 
int main() {
    int answer = 42; 
    printf("The meaning of life is %d");
}
```

```C 
int main() {int answer = 42; printf("The meaning of life is %d")} // please don't do this
```


While this freedom may allow experienced programmers to format their code however makes the most sense
to them, it can also lead to harder to understand code, especially in codebases maintained by multiple 
people with different coding styles (though using formatting tools helps a bit). 
Python sidesteps this issue entirely by forcing each statement on a separate line, preferring 
uniformity to flexibility in true Python fashion.


## Statement Separators
Although we've answered our leading questions we're not done yet. Now that we've established 
that imperative programs are essentially list of commands. It's interesting to note that not 
all languages use semicolons as statement terminators, some languages like Perl for example use 
semicolons as **statement separators**. That is, the semicolon is only really necessary when 
statement follows another. 


```perl 
sub one {
    say "Hello, World!" # no semicolon because it's a single statement
}


sub two {
    say "Hello, World!"; # semicolon
    say "Goodbye, Mars!" # last statement so it doesn't need a semicolon
}
```

With that, we've covered the main uses of semicolons for imperative languages but the real fun starts 
when we broaden our scope a bit.


## Expression-based languages

Not all languages are imperative. In my opinion, few of the ones are. Some languages, rather than issuing 
commands to the computer they describe the solution. Most of the terms in these programming languages are 
expressions rather than statements, that is, they return a value instead of doing something or other. I refer 
to these languages as **expression-based**, in these languages semicolons aren't always used to separate 
statements usually because they're a lot less statements going around. This section will be a brief survey 
on how semicolons are used in three of them: OCaml, LISP and Rust. 


### OCaml
In Ocaml, semicolons are more of a general purpose separator. They're used for separating list items, record 
fields and- surprise, surprise- statements. Statements in Ocaml are expressions that return `unit` 
(similar to void in C-like languages), using semicolons you can chain multiple statements together. 

```ocaml 
(** This is a comment*)

let fruits = ["banana"; "apple"; "orange"] (** This is a list*)

type Person = {
    name: string; 
    age: int;
}

let main = 
    do_something1; 
    do_something2; 
    print "Hello, World!"
```

### LISP 
For LISP and its descendants everything is a list and the lists only ever need 
to be separated by whitespace. Even when statements are used, it's pretty easy to just 
list them out. 

```LISP
(do 
    statement1 
    statement2 
    statement3)

```

### Rust
Rust is a bit of a special case in that it's more imperative than expression-based languages but 
not as imperative as imperative languages. Semicolons are used to "promote" expressions into statements. 


```rust 
// returns 42
fn func1() {
    42
}


// returns ()
fn func2() {
    42;
}
```

