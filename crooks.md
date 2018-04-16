# `vim`
Fix indententation to be uniform: `=`

Fix indententation to be uniform in whole file: `gg=G`

# `tmux`
The default prefix is `Ctrl + B`

Create new vertical pane: `prefix %`

Create new horizontal pane: `prefix "`

# `git`

Create a local branch and push to same-named remote branch ([SO thread](https://stackoverflow.com/questions/1519006/how-do-you-create-a-remote-git-branch/)):

    git config --global push.default current
    git push -u
