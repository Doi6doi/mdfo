# MDFO
A simple form format and utilities

MDFO stands for MD Form. It is a simple format for storing and optionally filling forms. Can be used for real time forms (like a math test), or even for configuration files. It is human readable, self-explanatory single text file. Besides the form itself, it can contain names of the sections, fields, and possible field values.

A form can be filled by hand with any text editor, or a html (or dialog, etc...) form filled can be generated of it. The filled data can be extracted, or validated. The form can be be stored and copied even in semi-filled state.

## Online editor and filler

Try the all-in-one online [form creator] and filler.

## Simple example

A simple example for a contact form:

```
# Contact us

Name: []
{name:req}

Email: []
{email:email req}

Age: []
{age:int(9-99)}

Employment: [] Employed [] Unemployed [] Student [] Retired [] Other
{employed:opt(e|u|s|r|o)}

Message: []
{message:req}

[] I have read the [Terms of Service](terms.html)
{terms: req opt}
```

It defines a contact forms with the following fields::
 - a required `name`
 - a required `email` which only accepts a syntactically correct e-mail address
 - an optional `age` in range(9..99)
 - a single-choosable optional `employed` field with 5 options
 - the required `message`
 - a required option that the user has read the terms

