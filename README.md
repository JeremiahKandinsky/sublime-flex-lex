## What's this

Sublime Text Syntax highlighting support for (GNU) flex files, you know,
for parsers and stuff. Tested on ST3.

## Installation

```Bash
# In linux
mkdir ~/.config/sublime-text-3/Packages/FlexLex
cp * ~/.config/sublime-text-3/Packages/FlexLex
```
You should see a new "Flex/Lex" syntax highlighter available
under the 'User' sub-menu in the List of highlighters at the
bottom right corner of the editor.

## Notes

Sublime's syntax highlighting is quite powerful, but not
quite powerful enough to handle everything found in .l files.

This Does:
- Syntax highlight the C/C++ code found within the %{ %} delimiters.
- Highlight definition names, in both the definitions and rules sections.

This Does not:
- Syntax highlight the C/C++ code for rule actions.
- Syntax highlight the regexp's found in the definitions/rules sections

If you wrap the C/C++ code normally found after the rules section
with the following comments (exactly!):

```
/\*\* BEGIN CPP_SOURCECODE \*\*/

 <... Your code here...>

/\*\* END CPP_SOURCECODE \*\*/
```

It will sort-of highlight that code as C/C++ code, but not very well.
It *should* work but... it doesn't. Perhaps a bug in ST.

## Tweaking

The `.YAML-tmLanguage` file is the grammar definition, you only need
this if you want to tweak the definitions, the compiled version is
the `.tmLanguage` file and thats is what Sublime uses.

See `http://docs.sublimetext.info/en/latest/extensibility/syntaxdefs.html`
For the guide on writing and compiling these YAML files.

## Why isn't this available from package manager?

Too many hoops to jump through. You're welcome to fork the repo and
[submit it](https://packagecontrol.io/docs/submitting_a_package) yourself.

## Why not use the one in the TextMate? ST is compatible you know.

Oh, you mean your google search came up with [this SO question](https://stackoverflow.com/questions/19136731/is-there-a-sublime-text-syntax-for-flex-and-bison)  too?
Imagine that.

This one's better.

## What about pull requests?

No thanks. Fork and have at it.
