---
title: "Vim paste weird indentation"
toc: true
toc_sticky: true
---

# Vim pasting without the weird indentation

### 📌 Issue
I wanted to paste the code from clipboard using vim, but when the code got longer, the formatting became super weird with a lot of tabs.

<br>

### 📌 Solution
It was actually really simple.

Before typing `i` to enter the insert mode, type `:set paste`.

If you go to insert mode after doing so, you'll be seeing `--INSERT (paste)--`. In this mode, pasing works the way you want it to!