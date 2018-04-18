# `vim`
Fix indententation to be uniform: `=`

Fix indententation to be uniform in whole file: `gg=G`

To replace sth. across several lines, you can use visual block and `c` (like below). For some reason, the change will only appear on the first line until you hit `Esc` and _then_ another key. [SO How to replace text in visual mode?](https://duckduckgo.com/?q=vim+visual+mode+replace&t=ffsb&ia=qa)

```
Ctrl v
jjj
c[do your thing]
Esc
```

# `tmux`
The default prefix is `Ctrl + B`

Create new vertical pane: `prefix %`

Create new horizontal pane: `prefix "`

# `git`

Create a local branch and push to same-named remote branch ([SO thread](https://stackoverflow.com/questions/1519006/how-do-you-create-a-remote-git-branch/)):

    git config --global push.default current
    git push -u

# misc
To view pdfs in terminal, use `less`. You may have to `eval $(lesspipe)` first ([Unix SE](https://unix.stackexchange.com/questions/36201/pdf-viewer-for-command-line-only)).

To unzip several archives, put quotes around the glob, e.g. "\*.zip". h/t [nixCraft](https://www.cyberciti.biz/faq/linux-unix-shell-unzipping-many-zip-files/)
