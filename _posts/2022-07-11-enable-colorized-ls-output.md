---
title: "Enable colorized `ls` output in terminal"
toc: true
toc_sticky: true
---
# See colorful `ls` output

### 📌 Check your shell
`ps -p $$`

Mine is `zsh`, so I would need to modify `.zshrc`.

If you're using bash, it would be `.bashrc`.

<br>

### 📌 Open and modify your shell configuration file

Open the shell configuration file with any text editor you like.

I used vim here.

`vim ~/.zshrc`

Then, add `export CLICOLOR=1`.

You can go to insert mode by pressing `i`, and add that line. When you're done, press `esc` and type `:wq` to save and exit.

<br>

### 📌 Then
`source ~/.zshrc`

Now when you type `ls`, you'll be able to see colorized output!