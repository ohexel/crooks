This is a collection of personal notes on how to achieve various small or not so small tasks in different utilities, mostly vim and tmux (and some git).

# `vim`
How to avoid the escape key? [Tips](https://vim.fandom.com/wiki/Avoid_the_escape_key) from the Vim Wiki. E.g. use `Ctrl+[` or `Alt/Meta+` `hjkl` (`Alt/Meta` implicitly sends an escape signal).

Some commandline terms:

- `%`: current file
- `:p`: path (e.g. of current file)
- `:h`: "head" of a path (i.e. the "inner-most" directory)

Change working directory to that of current file (for all windows): `:cd %:p:h`

Change working directory to that of current file (for the current window): `:lcd %:p:h`

Autocomplete: `C-p` or `C-n`

Fix indententation to be uniform: `=`

Fix indententation to be uniform in whole file: `gg=G`

To replace sth. across several lines, you can use visual block and `c` (like below). For some reason, the change will only appear on the first line until you hit `Esc` and _then_ another key. [vi SE How to replace text in visual mode?](https://duckduckgo.com/?q=vim+visual+mode+replace&t=ffsb&ia=qa) [Vim wikia Search and replace in visual](http://vim.wikia.com/wiki/Search_and_replace_in_a_visual_selection)

```
Ctrl v
jjj
c[do your thing]
Esc
```

Compile latex files in vim: vimtex plugin + `:vimtexCompile`

See content of all registers: `:registers`

Uppercase word w visual mode

    vawU

... without visual mode

    gUiw

Upper/lowercase word

    gUaw guaw

Uppercase line w visual mode

    VU

Uppercase a whole Sentence

    gUis

... a whole Paragraph

    gUip

... Inside of quotes

    gUi"

... Inside of a tag

    gUit

How to escape a percent sign that is preceded by a digit?

```
`%s/\(\d\+\)%/\1\\%/g`
```

# `tmux`
The default prefix is `Ctrl B`

Create new vertical pane: `prefix %`

Create new horizontal pane: `prefix "`

# `git`

Remove local branch: `git branch -d local-branch`

Remove remote branch after removing local branch: `git push origin :remote-branch`

Remove remote branch: `git push origin --delete remote-branch`

Update local list of remote branches (e.g. when they got deleted from somewhere else): `git remote update origin --prune`

Only move tracked files

    git mv -k SOURCE... DESTINATION

Only move tracked files

    git mv -k SOURCE... DESTINATION

See git history for files that have been moved

    git log --follow ./path/to/file

Create a local branch and push to same-named remote branch ([SO thread](https://stackoverflow.com/questions/1519006/how-do-you-create-a-remote-git-branch/)):

    git config --global push.default current
    git push -u

Add new remote origin (here hosted at gitlab; example courtesy of gitlab):

    cd existing_repo
    git remote rename origin old-origin
    git remote add origin git@gitlab.com:ohexel/XXXX.git
    git push -u origin --all
    git push -u origin --tags

Change default remote on checked out branch: `git branch --set-upstream-to new-remote/currently-checked-out-branch`

# Other people's cheat/reference sheets

[Bram Moolenaar's Seven habits of effective text editing](http://www.moolenaar.net/habits.html)

[tmux, alvin alexander](https://alvinalexander.com/linux-unix/tmux-cheat-sheet-commands-pdf)

[tmux, sam atkinson](http://atkinsam.com/documents/tmux.pdf)

[tmux intro, ham vocke](http://www.hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/)

[tmux customizing guide, ham vocke](http://www.hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/)

# misc
Consider mapping `Esc` or `Ctrl` in vim to `CapsLock`. You can map `CapsLock` to `push both Shifts` like so: `setxkbmap -option "shift:both_capslock"`

To view pdfs in terminal, use `less`. You may have to `eval $(lesspipe)` first ([Unix SE](https://unix.stackexchange.com/questions/36201/pdf-viewer-for-command-line-only)).

To unzip several archives, put quotes around the glob, e.g. "\*.zip". h/t [nixCraft](https://www.cyberciti.biz/faq/linux-unix-shell-unzipping-many-zip-files/)

[Latex in R Markdown](http://www.calvin.edu/~rpruim/courses/m343/F12/RStudio/LatexExamples.html)

[R Markdown examples](http://statpower.net/Content/310/R%20Stuff/SampleMarkdown.html)

To convert markdown with `utf8` characters with `pandoc` use the `-s` or `-ascii` flags.

# Tutorials and explanations

[registers in vim](https://medium.com/vim-drops/vim-registers-the-powerful-native-clipboard-19b1c97891bd)

[system clipboard in vim](http://vim.wikia.com/wiki/Accessing_the_system_clipboard).

[Define default applications via `mime`](https://linuxcommando.blogspot.fr/2014/03/how-to-specify-default-applications-for.html).

[How to use bash history](https://www.digitalocean.com/community/tutorials/how-to-use-bash-history-commands-and-expansions-on-a-linux-vps)

# Plugins, repositories, etc.

[preview vim registers](https://github.com/junegunn/vim-peekaboo)

[permanently show vim registers](https://github.com/dahu/vim-lotr)

[easily create tables in vim](https://github.com/dhruvasagar/vim-table-mode)

[CL spreadsheet tool](http://visidata.org/)

[web search in rofi](https://github.com/miroslavvidovic/rofi-scripts/blob/master/web-search.sh)
