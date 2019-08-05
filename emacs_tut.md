## Extending the command set

`C-x` - character extend
`M-x` - named command extend

**[basic keys](http://ergoemacs.org/emacs/emacs_keys_basics.html)**

C-x-u / C-_ -- undo


## Buffers

C-x C-f -- find/create a file and also switch between buffers
C-x C-b -- List buffers
C-x k to kill (close) a buffer. Automatically opened windows are usually closeable with “q”.
C-x b {buffer-name} - switch to buffer {buffer_name}
C-x s - Save some buffers

C-z -- exit Emacs *temporarily*--so that you can go
    back to the same Emacs session afterward

> `C-x 4 C-f {file_name}` -- See the specified file appear in the
> bottom window. The cursor goes there, too.

- C-g - cancel prompts. Later we’ll remap the escape key to do the same which anyone coming from Vim will need to retain its sanity.
- C-y: yank/paste. The only way to paste on the modeline even when you’re using Evil.

`M-%` - replace string (y - replace, n - skip, ! - do all replacements)
`M-;` - comment / uncomment region
`C-s C-s` - saerch the same word searched last time
`C-s C-w` - search the word under the cursora (type `C-w` multiple tiles to expand word selection)


## Commands

- `M-x visual-line-mode` - toggle long lines wrapping (like set wrap/nowrap in Vim)

- `M-x delete-trailing-whitespace` - delete trailing white spaces in the whole buffer





## Auto save

Emacs periodically writes an "auto save" file for each file that
you are editing. The auto save file name looks like "#{file_name}#". 
When you save the file, Emacs deletes its auto save file.

If the computer crashes, you can recover it by opening it again and then typing
M-x recover file RET


## Editing modes

**To view documentation on your current major mode, type C-h m.**

`M-x text mode <RET>` - M-f and M-b now treat apostrophes as part of
words. In Fundamental mode, M-f and M-b treated apostrophes as
word-separators.

---------

**Major modes** are called major because there are also minor modes.
**Minor modes** are not alternatives to the major modes, just minor
modifications of them.  Each minor mode can be turned on or off by
itself, independent of all other minor modes, and independent of your
major mode.  So you can use no minor modes, or one minor mode, or any
combination of several minor modes.

You can have a single major mode and multiple minor modes
**mmm-mode** - allows you have multiple major modes.
A major mode is similar to _set filetype_ from Vim, and a minor mode
is similar to a plugin like _vim-surround_, which spans all
filetypes.

The biggest difference is that major modes in Emacs often change key
bindings radically.

---------

**Auto Fill** mode, Emacs breaks the line in between words automatically
whenever you insert text and make a line that is too wide. (`M-x auto fill mode <RET>`)

Default margin is 70 chars, but you can change it: `C-x f {number}`

M-q -- re-fill the paragraph under cursor


## Recursive editing levels

To get out of the recursive editing level, type <ESC> <ESC> <ESC>.
That is an all-purpose "get out" command.  You can also use it for
eliminating extra windows, and getting out of the minibuffer.

> Type M-x to get into a minibuffer; then type <ESC> <ESC> <ESC> to get out.


## Packages

`M-x package-list-packages RET` -- open up the package manager
buffer. Inside this buffer instead of `C-p` and `C-n` you can use `n`
and `p` instead and `i`nstall, `d`elete and `h`elp. Emacs is modal.

the customize buffer, via `M-x customize-group RET` also sets up its
own modal bindings; `TAB` for example will jump to the next option.

M-x list-packages -- see all packages


## Themes

`M-x load-theme RET` - check the available themes. Then put in .emacs:
(load-theme 'misterioso t).

M-x customize-themes
