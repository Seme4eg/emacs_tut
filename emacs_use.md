## BUFFERS

C-x b {buf_name} -- create new buffer with {name}


## MACRO

f3 --> do things --> f4 -- record a macro (f4 - call macro) 

C-= - highlight syntactical section, repeat (select function with that shortcut and press `tab` to indent properly)

C-x C-+/- -- increate/decrease font size

M-x customize-themes

M-x list-packages -- see all packages

C-h i -- list all commands
C-h b -- **list all keybindings**

M-x shell -- open shell inside emacs **useful**

M-x visual-line-mode -- instead of hard word wrap there will be soft wrap (words will not break up)

M-x menu-set-font -- change font if can

M-x linum-mode -- show line numbers


---

no restarting emacs when add to init file:

- `M-x eval-requion` -- evals selected lines of code in emacs

- `M-x eval-buffer` -- evaluete code in cur. line

- `M-x load-file` (then 2 times RET) -- reload any file (most often .emacs) without restarting Emacs


`M-x revert-buffer` - “refresh” a opened file to its saved state


`C-h l` - shows all commands called before (including function names)
