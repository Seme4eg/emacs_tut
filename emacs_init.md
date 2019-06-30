vi mode in bash or zsh ?
org mode (watch google talk about it) (jourmen astrano - author / curston dominic)?
neovim..
what vim can do, what emacs can't?
power line?

vim vs emacs:

- async processing, terminal emulation (both this things neovim can do as well,
  but essentially neovim is chasing emacs). Emacs can also be decoupled server
  and client, you can run Emacs as a daemon and it is not like vim's
  client-server where one instance of vim acts like a client and the other acts
  like a server. Emacs is 12Mb core with none of the List extensions. The Emacs
  client is 29K, it is a lightweight client, it just displays what the server
  tells it to do

- Emacs has different GUI implementation (VIM is a terminal implementation),
  that means it can support different font sizes, graphics, line drawing, swg,
  displaying pdfs

When was VIM and Emacs invented? emacs & vi - 1976, vim - 1991

- Emacs isn't right for everyone
    + it got big footpring
    + is memory intensive
    > so if you are remoting often, Emacs is not the option, VIM is
    > lightweight, it is fast 
- Vim is not for everyone as well
    + emacs got vim inside it so you can use VIM's powers inside Emacs

20:33 - Emacs first demonstration

Emacs has **Web Mode** - is one of several mods, that support multiple modes at
the same time, it does what VIM has trouble with for a long time - is supports
templates

Emacs emulates only ZSH terminal?

Emacs package Magit (or magic) - Emacs interface to Git (demonstration 28:18)
and then 30:10

Gtags - generates tag file, which allows you to find occurances of
vars/functions in the whole project

31:20 - **snippets** (package - _yah_ snippet, which is almost the same as
_ulty snips_)

**Helm** package - narrowing completion framework (`ctrl + p` for every single list in emacs ever)

