---
title: "How to undo git commits"
toc: true
toc_sticky: true
---

# Undo git commits

### 📌 Undo only a specific commit
`git revert --no-commit b2d25ae`

<br>

### 📌 Undo every commit after `b2d25ae`

`git revert --no-commit b2d25ae..HEAD`
`git commit`


### 📌 Then
`git commit`