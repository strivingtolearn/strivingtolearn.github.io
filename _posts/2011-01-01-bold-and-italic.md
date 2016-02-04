---
layout: default
---

<!-- I escape the unmatched underscores and asterisks because it breaks my vim
     highlighting plugin from https://github.com/tpope/vim-markdown. This
     appears to have no effect on the generated html. -->

Bold can be two asterisks (\*) or two underscores (\_). Italic can be one
asterisk or one underscore.

`**bold**`	=	**bold**

`__bold__`	=	__bold__

`*italic*`	=	*italic*

`_italic_`	=	_italic_

### All manner of mixing should work

`**mixed *italic* in bold**`	=	**mixed *italic* in bold**

`**mixed _italic_ in bold**`	=	**mixed _italic_ in bold**

`__mixed *italic* in bold__`	=	__mixed *italic* in bold__

`*mixed **bold** in italic*`	=	*mixed **bold** in italic*

`_mixed **bold** in italic_`	=	_mixed **bold** in italic_

`*mixed __bold__ in italic*`	=	*mixed __bold__ in italic*

Generally speaking, you might want to use asterisks as [GitHub Flavored
Markdown](https://help.github.com/articles/github-flavored-markdown/) differs
slightly with how underscores are parsed.

Vanilla markdown:
<!-- I have to cheat here since gfm doesn't render the _ as italic -->
`test_italics_here_`	=	test*italics_here*

GitHub markdown:
`test_italics_here_`	=	test_italics_here\_

<!-- vim: set tw=80 ts=2 sw=2 et: -->
