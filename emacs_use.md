f3 --> do things --> f4 -- record a macro (f4 - call macro) 

C-x C-+/- -- increate/decrease font size


## Customize

`M-x customize` - enter customization menu

`M-x customize-group` - enter customization menu for specific group

> `M-x customize-group` --> then enter 'package'

M-x customize-themes

M-x menu-set-font -- change font if can


## Packages

`M-x list-packages` - see all packages

while in list of packages:

`Shift-u` - mark any packages available for upgrade --> `x` to install
- `i` -- mark package
- `x` -- install marked package


C-h i -- list all commands
C-h b -- **list all keybindings**
> or just go [here](https://www.gnu.org/software/emacs/refcards/pdf/refcard.pdf)

`C-h k {any key binding}` -- get help on a particular key combination

M-x shell -- open shell inside emacs **useful**

M-x visual-line-mode -- instead of hard word wrap there will be soft wrap (words will not break up)

M-x linum-mode -- show line numbers


---

no restarting emacs when add to init file:

- `M-x eval-requion` -- evals selected lines of code in emacs

- `M-x eval-buffer` -- evaluete code in cur. line

- `M-x load-file` (then 2 times RET) -- reload any file (most often .emacs) without restarting Emacs


`M-x revert-buffer` - “refresh” a opened file to its saved state


`C-h l` - shows all commands called before (including function names)



## Windows

`M-x menu-set-font` - set font if available


