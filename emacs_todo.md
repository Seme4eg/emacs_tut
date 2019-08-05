set up and understand how **helm** package works, currently i've got some basic helm setup in `.emacs`

understand why this doesn't work:

;; automatically save/restore sessions
(desktop-save-mode 1)


set up shortcuts with _leader_ character


does `set filetype={file_type}` works in emacs?

`set tabstop=2` - works as well in emacs?

VIM, to fix indentation in file (spaces to tabs):

- :set noexpandtab
- :retab! // can be used also on visual block
- :set expandtab // convert tabs back to spaces


delete all empty lines:

`:g/^$/d` -- can be also applyed to just several lines

`{motion}i{block}` - do {motion} with text within {block}

> `=i{` - indent text within the scope (or `vi{` ..)


---

in emacs - do [this](https://emacsredux.com/blog/2013/04/28/switch-to-previous-buffer/)

how to set autoformatting in emacs, like VIM's `set formatoptions=...`?

if i'll get to many packages in emacs - install _use-package_

set the mapping with leader (<leader> + 'e') to open .emacs file in a new buffer

bind vs to C-w v and sp to C-w s and swap windows to C-c r
