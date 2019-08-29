+++
title =  "Best of Python 3 f-strings"
date = 2019-08-27T23:29:18+05:30
tags = ["tech"]
featured_image = ""
description = "Python f-string Primer"
toc = true
show_reading_time = true
+++

This piece is primarily meant for those new to Python. These include mathematicians, economists, and so on who want to use Python within a Jupyter environment. Here is a quick guide on how to make [Best of Jupyter](https://github.com/NirantK/best-of-jupyter).

## Quick Primer

If you are familiar with earlier Python versions, here are my top picks on how to move from .format () to this new one:

<script src="https://gist.github.com/NirantK/9d667034ef7feac484c21528251decbb.js"></script>

## f-string Magic

f-strings are how you should use print statements in Python. It is fairly reminiscent of LaTeX in it’s inline notation:

<script src="https://gist.github.com/NirantK/345e8d846bbc13a18caec0e40b47fde3.js"></script>

Notice how the variable _name_ can now be used inline. This is a simple and easy to use syntax: just include the variable in surrounding _{}_ while marking the string type as f-string using the ‘_f_’ in the beginning.

_Note to the advanced programmer_: 

‘f’ may be combined with ‘r’ to produce raw f-string which can be used inside regex or similar functions. ‘f’ may not be combined with ‘u’, this is because all Python3.6+ strings are Unicode by default now. This means, you can write fstrings in Hindi, Chinese, French, Korean and atleast 10 other languages.

> You can write fstrings in Hindi, Chinese, French, Korean and any language covered by Unicode.

But why are these called formatted-strings in the first place? Because you can use with some cool formatting hacks.

## Simplified Alignment and Spacing

Have you ever tried creating a table such as that for logging or visualization? Arranging the elements becomes a nightmare with several `\t` tab characters flying around.

This is much easier with Python f-strings using the colon ‘:’ operator, followed by a an alignment operator and field width value.

There are atleast 3 alignment operator: < for left aligned, > for right aligned, and ^ for center aligned. Refer the code example:

<script src="https://gist.github.com/NirantK/c20e7b2e3cc302a967171c327089a5db.js"></script>

You also have support for decimal truncation and similar standard formatting utilities:
<script src="https://gist.github.com/NirantK/3faa8e43ba0a376e56210c92fb3740e2.js"></script>

You might notice something interesting here: width and precision are automatically picked up from the scope. This means you can calculate width and precision using screen width or other inputs from system and use that.

## Full Python Expressions Support

The above is only possible because the expression inside {} is actually being evaluated, or in programming terms: being executed.

<script src="https://gist.github.com/NirantK/413f48601f9e22887e74f8b263179fa5.js"></script>

This implies, that you can make any function call from within those {}.

Though, you should avoid doing this in practice very often because it might make your debugging very difficult. Instead, store the returned value from function in a variable and then add the variable in a fstring print statement.

Those coming from functional programming might miss their lambda functions. Don’t worry, Python has you covered:

## Lambda Functions in f-strings

<script src="https://gist.github.com/NirantK/c770b55f0f0a6941a58ed751b86f535e.js"></script>

# Summary

- f strings mean you can include variables and function calls inside your print statements
- Inline variables: these are easier to read and debug for the developer
- **_Use f-strings when you can_**!