## Magit

> ref: https://www.youtube.com/watch?v=zobx3T7hGNA
> ref: https://www.youtube.com/watch?v=vQO7F2Q9DwA

`<leader>gi` (`M-x magit-init`) -- init rep
`<leader>gs` (`M-x magit-status`) -- run magit main interface

_While in magit interface_:

- `n` -- next line
- `p` -- prev line
- `s` -- stage file (or if hover category - stage all files in this category
- `k` -- discard changes
- `i` -- add this file to .gitignore
- `tab` -- view changes in file --> <RET> on needed line --> edit --> go to prev buffer --> `g` to **refresh**
- `g` -- refresh the state of changed files
- `c c` -- commit (after wrote commit `C-c C-c`)
- `l l` -- short log (shows latest commits)
- `h` -- **help** (shows all keys)
- `$` -- pop up status messages
- `b c` -- create new branch


_Working with Remote Repository_:

- `M a` -- add remote rep
- `P p` -- push
- `m m` -- merge
- `F F` -- fetch
- `e` -- resolve conflicts --> `n` --> choose A/B --> save

### Commits (canceling / changing / squashing / splitting)

**Canceling commit message**:

`X` --> choose type of reset u want (i needed soft, so i chose `s`) --> **do not choose any of shown**, just type HEAD~1 in minibuffer at bottom of the screen!

**Changing commit message**:

`l l` --> cursor under wrong commit --> `r w` to reword a commit (then write new one)

**Squashing commits**:

make 1 commit from _N_ last ones:

`l l` --> go to the oldest of _N_ --> `r i` ('i' for interactively)
	  --> read the cheat sheet there and do what you need --> `C-c C-c`

> or if you need to squash all unpushed commits instead of `r i` do `r l`
> and keep in mind that there all changes are reversed (old commits are at the top)
> prob. what you need is `s` (squash)

**Splitting commit**:

`l l` --> hover needed one --> `r m` --> @ sign shows cur. HEAD
	commit, move HEAD one step before it by moving cursor to prev. one and
	press `x` --> choose `master~1` --> go to main screen and commit
    everything separately --> `r r` to continue rebase

---

### Rebasing

checkout to needed branch --> `r e` and choose master ('e' for
	elsewhere) -- put cursor on the conflict file and press `e` --> select
	needed diff --> `b` to choose variant B (for instance) --> `q` (quit
	Ediff) --> on main magit screen press `g` to **refresh** it --> `r r`
	(continue rebase)

> nice reference is shown in [this](https://www.youtube.com/watch?v=vQO7F2Q9DwA)
> video, **after** 10:38

**Bisecting** - find the last commit that fucked up everything

> https://www.lvguowei.me/post/magit-tutorial-bisect/




### Patch another branch's some files

`D`iff two branches --> move focus by `N`, `P` --> focud needed diff-item --> `a`pply

> same way works for new file created on dif. branch



## Helm

> https://emacs-helm.github.io/helm/

all key bindings in /emacs_init/emacs_kbd.el file

**Important**: In any helm session, as soon there is candidates in the
helm buffer `C-h m` pops an org buffer with detailed documentation
about current command and more generalized infos about helm.

That's pretty much the only thing u need to know about _Helm_



## Projectile & helm-projectile

https://github.com/bbatsov/projectile

> helm-projectile -- helm integration for Projectile

`<leader>pf` - projectile-find-file -- open file in project (porject is considered to be a git rep

to make projectile ignore some files create `.projectile` file and put there regexp like in `.gitignore`:
	-*.md
	-.*

> where `-` means **ignore** (`-*.md` means ignore all .md files)

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
