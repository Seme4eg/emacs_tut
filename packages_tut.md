## Magit

> ref: https://www.youtube.com/watch?v=zobx3T7hGNA

`<leader>gi` (`M-x magit-init`) -- init rep
`<leader>gs` (`M-x magit-status`) -- run magit main interface

_While in magit interface_:

- `n` -- next line
- `p` -- prev line
- `s` -- stage file (or if hover category - stage all files in this category
- `c c` -- commit (after wrote commit `C-c C-c`)
- `l l` -- short log (shows latest commits)
- `h` -- **help** (shows all keys)

_Working with Remote Repository_:

While in magit interface:

- `M a` -- add remote rep
- `P p` -- push
- `m m` -- merge

### Commits (changing / squashing / splitting)

**Changing commit message**:

`l l` --> cursor under wrong commit --> `r w` to reword a commit (then write new one)

**Squashing commits**:

make 1 commit from _N_ last ones:

`l l` --> go to the oldest of _N_ --> `r i` ('i' for interactively)
	  --> read the cheat sheet there and do what you need --> `C-c C-c`

**Splitting commit**:

`l l` --> hover needed one --> `r m` --> @ sign shows cur. HEAD
	commit, move HEAD one step before it by moving cursor to prev. one and
	press `x` --> choose `master~1` --> go to main screen and commit
    everything separately --> `r r` to continue rebase

---

`b c` --> create new branch

**Rebasing**:

checkout to needed branch --> `r e` and choose master ('e' for
	elsewhere) -- put cursor on the conflict file and press `e` --> select
	needed diff --> `b` to choose variant B (for instance) --> `q` (quit
	Ediff) --> on main magit screen press `g` to **refresh** it --> `r r`
	(continue rebase)

**Bisecting** - find the last commit that fucked up everything

> https://www.lvguowei.me/post/magit-tutorial-bisect/



## Helm

> https://emacs-helm.github.io/helm/

all key bindings in /emacs_init/emacs_kbd.el file

**Important**: In any helm session, as soon there is candidates in the
helm buffer `C-h m` pops an org buffer with detailed documentation
about current command and more generalized infos about helm.

That's pretty much the only thing u need to know about _Helm_



## Projectile

https://github.com/bbatsov/projectile

Learn how to do following things:

    jump to a file in project
    jump to a project buffer
    kill all project buffers
    replace in project
    multi-occur in project buffers
    grep in project
    regenerate project etags
    visit project in dired
    run make in a project with a single key chord



## Dired

comes preinstalled with emacs

`C-x C-f` (def shortcut) <RET> -- open dired buffer of cur dir

**Shortcuts in this dir**:

`d` - mark file for deletion
`~` - mark all backup files for deletion
`x` - execute the action (delete all marked files for instance)
`+` - create new file/dir **or** `C-x C-f` in the dir and enter name of new file
`g` - refresh contents of buffer
`!` - (while pointing at any file) run shell command on this file (! index.html firefox)
`C` - copy file and type new name for it
`R` - rename file
`s` - change sorting order of the dir.
`A` - search for regexp in files in cur dir --> then press `M-,` to go to next match
`C-x C-q` - make dired buffer editable --> after changes are done `C-c C-c`

to operate on multiple files - **mark** them:
`m` - mark file / dir
`u` - unmark file
`U` - unmark all files
`t` - toggle marks in cur dir

**to work only on files in cur. dir.**:
`* /` - mark all directoryes --> `t` - toggle marks (will mark all files and unmark all dirs)

> `C-h i` --> 'Emacs' --> 'Dired' -- **documentation** for Dired
