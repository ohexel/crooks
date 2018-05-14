This is a collection of personal notes on how to achieve various small or not so small tasks in different utilities, mostly vim and tmux (and some git).

# `vim`
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


# `tmux`
The default prefix is `Ctrl B`

Create new vertical pane: `prefix %`

Create new horizontal pane: `prefix "`

# `git`

Create a local branch and push to same-named remote branch ([SO thread](https://stackoverflow.com/questions/1519006/how-do-you-create-a-remote-git-branch/)):

    git config --global push.default current
    git push -u

# Other people's cheat/reference sheets

[tmux, alvin alexander](https://alvinalexander.com/linux-unix/tmux-cheat-sheet-commands-pdf)

[tmux, sam atkinson](http://atkinsam.com/documents/tmux.pdf)

[tmux intro, ham vocke](http://www.hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/)

[tmux customizing guide, ham vocke](http://www.hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/)

# misc
To view pdfs in terminal, use `less`. You may have to `eval $(lesspipe)` first ([Unix SE](https://unix.stackexchange.com/questions/36201/pdf-viewer-for-command-line-only)).

To unzip several archives, put quotes around the glob, e.g. "\*.zip". h/t [nixCraft](https://www.cyberciti.biz/faq/linux-unix-shell-unzipping-many-zip-files/)

[Latex in R Markdown](http://www.calvin.edu/~rpruim/courses/m343/F12/RStudio/LatexExamples.html)

[R Markdown examples](http://statpower.net/Content/310/R%20Stuff/SampleMarkdown.html)
