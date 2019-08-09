vi mode in bash or zsh ?
Emacs emulates only ZSH terminal?
org mode (watch google talk about it) (jourmen astrano - author / curston dominic)?

- async processing, terminal emulation. Emacs can also be decoupled server
  and client, you can run Emacs as a daemon and it is not like vim's
  client-server where one instance of vim acts like a client and the other acts
  like a server. Emacs is 12Mb core with no extensions. The Emacs
  client is 29K, it is a lightweight client, it just displays what the server
  tells it to do

- Emacs has different GUI implementation (VIM is a terminal implementation),
  that means it can support different font sizes, graphics, line drawing, swg,
  displaying pdfs

- Emacs isn't right for everyone
    + it got big footprint
    + is memory intensive
    > so if you are remoting often, Emacs is not the option, VIM is lightweight & fast

20:33 - Emacs first demonstration

Gtags - generates tag file, which allows you to find occurances of
vars/functions in the whole project

31:20 - **snippets** (package - _yah_ snippet, which is almost the same as
_ulty snips_)
