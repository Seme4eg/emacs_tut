# Introduction

all invormation in this file explains only emacs itself, it doesn't use 'evil-mode', because i myself know vim
and therefore suppose that this 'tutorial' is bein' read by ppl, who know vim as well

## Why emacs over vim?
- async processing, terminal emulation. Emacs can also be decoupled server and client, you can run Emacs as a
  daemon and it is not like vim's client-server where one instance of vim acts like a client and the other
  acts like a server. Emacs is 12Mb core with no extensions. The Emacs client is 29K, it is a lightweight
  client, it just displays what the server tells it to do

- Emacs has different GUI implementation (VIM is a terminal implementation), that means it can support
  different font sizes, graphics, line drawing, swg, displaying pdfs

- Emacs isn't right for everyone
  + it got big footprint
  + is memory intensive
  > so if you are remoting often, Emacs is not the option, VIM is lightweight & fast

## Basics
First: [make CapsLock be ctrl](https://www.emacswiki.org/emacs/MovingTheCtrlKey)

> i just did `setxkbmap -option ctrl:nocaps` (in terminal) (only for Unix systems)

`C-x` - character extend

`M-x` - named command extend

**[basic keys](http://ergoemacs.org/emacs/emacs_keys_basics.html)**

- `C-x u` / `C-_` -- undo
- `C-g` - cancel prompts. use it if u got in any unknown situation
- `C-y` - yank/paste. The only way to paste on the modeline even when you’re using Evil.
- `M-%` - replace string (y - replace, n - skip, ! - do all replacements)
- `M-;` - comment / uncomment region
- `C-s C-s` - saerch the same word searched last time
- `C-s C-w` - search the word under the cursora (type `C-w` multiple tiles to expand word selection)
- `C-z` - exit Emacs *temporarily*--so that you can go back to the same Emacs session afterward

> Automatically opened windows are usually closeable with “q”.

**getting help / documentation:**
- `C-h f[unction]/k[ey]/m[ode]` - ..
- `C-h a` - get a help on a command
- `C-h i/b` - list all commands/keybindings

> or just go [here](https://www.gnu.org/software/emacs/refcards/pdf/refcard.pdf)


# Navigation (buffers/windows(tabs))
## Buffers
- `C-x C-f` - find/create a file and also switch between buffers
- `C-x C-b` - List buffers
- `C-x b` - go to buffer
- `C-x k` - kill (close) a buffer.
- `C-x b {buffer-name}` - switch to buffer {buffer_name}
- `C-x s` - Save some buffers

### Ibuffer
`<leader> bm` - current shortcut for _ibuffer_

`?` - **everything** u need to know

### Finding in buffers
`M-x occur` - find all lines in cur. file that match regexp
`M-x multi-occur-in-matching-buffers` - find regexp in needed buffers

## Tabs
There are no tabs in emacs initially, but there are windows configurations (

> it is possible to configure tabs in emacs, but they won't be as flexible as in vim, or that'll take lots of effort to achieve, which is not worth it, here is some info tho:
> [tabbar package customisation](https://emacs.stackexchange.com/questions/10081/browser-style-tabs-for-emacs)
> [tabbar emacswiki page](https://www.emacswiki.org/emacs/TabBarMode)

## Windows
`C-x 0` - close window cursor is in
`C-x 1` - close other windows

### window configuration
`C-x r w {register}` - save cur window and buffer position into register
`C-x r j {register}` - reapply saved window config

(evil-leader/set-key "cs" 'window-configuration-to-register)
(evil-leader/set-key "cr" 'jump-to-register)

# Editing modes

**Major modes** are called major because there are also minor modes.

**Minor modes** are minor modifications of major modes. Each minor mode can be turned on or off by itself,
independent of all other minor modes, and independent of your major mode.

> The biggest difference is that major modes in Emacs often change key bindings radically.

- _mmm-mode_ - allows you have multiple major modes.
- _Text Mode_ - M-f and M-b now treat apostrophes as part of words. In Fundamental mode, M-f and M-b treated
  apostrophes as word-separators.
- _Auto Fill_ mode, Emacs breaks the line in between words automatically whenever you insert text and make a
  line that is too wide
- _Web Mode_ - one of several mods, that support multiple modes at the same time, **it supports templates**

**Set file to open in a major mode (like set filetype in VIM):**

[link](http://ergoemacs.org/emacs/emacs_auto-activate_a_major-mode.html)

# Packages
[here](https://github.com/emacs-tw/awesome-emacs) is big source of different pkgs

`M-x list-packages` - open up the package manager buffer. While in it:
- `h`elp -- see all possible commands (not many)
- `Shift-u` - mark any packages available for upgrade --> `x` to install

`M-x package-autoremove` - remove no longer needed packages

`M-x list-packages` - see all packages


# Customization & Themes

- `M-x customize` - enter customization menu
- `M-x customize-group [package_name]` - enter customization menu for specific group
- `M-x menu-set-font` - change font if can
- `M-x load-theme RET` - check the available themes
- `M-x` -> customize-themes


# Terminal

if you already have emacs session running, but for some reason want to open new file in emacs from terminal,
`emacsclient {file_name}` will open the file in existing emacs session, but in order for that to work you need
to go `M-x customize` --> search for 'server' --> set _Server Mode_ **on** and save it for future
sessions. After opening this file in existing emacs session `C-x #` after you done with it so the terminal
process ends

**Terminal inside emacs**:

`M-x term` - open terminal, but **don't** use this one
`M-x ansi-term` - faster, better, supports starting cursor applications etc..

> in 'char' mode ansi-term behaves like a terminal, in line mode it behaves like a buffer
> which means you can copy, edit stuff etc..

`M-x shell` - another way of opening terminal in emacs
`M-x eshell` - open shell written in emacs lisp

> in order to be able open multiple terminal in emacs:
> 0) install extension for terminal multiplexing 'tmux'
> 1) install pkg 'multi-term' and use `M-x multi-term`


# Macro

- `f3 (do things) f4` - record a macro (`f4` - call macro)
- `M-x name-last-kbd-macro` - store last used macro for future sessions
- `M-x insert-keyboard-macro` - insert a macro by its name


# Additional info

`C-h l` - shows all commands called before (including function names)

`C-c C-o` - open link below cursor (in default browser)

`TAB / Shift + TAB` in any `.md` file folds and unfolds headers

Default margin is 70 chars, but you can change it: `C-x f {number}`
M-q -- re-fill the paragraph under cursor

`C-x C-f /sudo::/path/to/file/` - **Edit file with super-user rights:**


## Some useful commands (M-x)

**Searching across opened buffers**:
- `multi-occur` - gives you fine control by prompting for each buffer to use
- `multi-occur-in-matching-buffers` - lets you enter a regexp to match file names

`revert-buffer` - “refresh” a opened file to its saved state

`visual-line-mode` - toggle long lines wrapping (like set wrap/nowrap in Vim)

`delete-trailing-whitespace` - delete trailing white spaces in the whole buffer

`recover file` - recover current file from 'autosave file'

`visual-line-mode` - instead of hard word wrap there will be soft wrap (words will not break up)

`linum-mode` - show line numbers

`menu-set-font` - set font if available

`goto-char` - go to buffer position in file (**useful** when debugging emacs init files)

After changing **any** config file:
- `C-x C-e` - eval expression (place cursor at the end of this expression)
- `eval-reguion` -- evals selected lines of code in emacs
- `eval-buffer` -- evaluete code in cur. line
- `load-file` (then 2 times RET) -- reload any file (most often .emacs) without restarting Emacs

`list-command-history` - show all commands history

- `ediff-current-file` - see changes made to a modified buffer since last save (press '?' to see help while in
this mode)
- `diff-buffer-with-file` - same

`butterfly` - [reference](http://lifegoo.pluskid.org/wp-content/uploads/2008/02/real_programmers.png)

**when typing in russian, but need to have all emacs shortcuts working just set input method to RU and chill:**

- `C-x RET C-\ method RET` - Select a new input method for the current buffer (set-input-method)
  ([docs](https://www.gnu.org/software/emacs/manual/html_node/emacs/Select-Input-Method.html#Select-Input-Method))
- `C-\` - enable or disable use of the selected input method (toggle-input-method).
