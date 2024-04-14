---
title: Miscellaneous Notes
created: 2023-09-03 08:46
updated: 2024-04-14T00:24
authors:
  - Edmund Leibert III
tags:
  - 🔴-academic/📚-educational-resource/name/🗒️-vim/🔖/miscellaneous-notes
  - 🔴-academic/📚-educational-resource/format/miscellaneous
  - 🔴-academic/📚-educational-resource/discipline/computer-science/technology/vim
  - study-note
cards-deck: 🔴 Academic::📚 Educational Resource::🗒️ Vim::Miscellaneous Notes
banner: "![[https://i.imgur.com/shEPtb6.jpg]]"
banner_y: 0
---

# Miscellaneous Notes

---

> [!INFO]+ Note 
> This **page** contains **miscellaneous** _scratch notes_ pertaining to **[Vim](https://www.zotero.org/)** [@brammoolenaarWelcomeHomeVim].
> 
> These notes are primarily structured in a Q&A format, making it easy to follow and learn. Corresponding [**Anki**](https://apps.ankiweb.net/) flashcards are available, enabling efficient revision and reinforcement of the concepts [@ankitectsAnkiPowerfulIntelligent].

---

> [!INFO]+ 
> **Previous Notes**:
> 

---

﹇<br>
As of Feb. 10, 2024 04:01:20 PM, how can you find and replace text in Vim?

#anki-card 

In Vim, you can find and replace text using the `:substitute` command, often shortened to `:s`. Here’s the general syntax:

```vim
:[range]s/{pattern}/{string}/[flags] [count]
```

- `range`: Specifies the lines to operate on. If no range is given, the command operates on the current line.
- `pattern`: The text you want to find.
- `string`: The text you want to replace the pattern with.
- `flags`: Modify the behavior of the command. For example, `g` replaces all occurrences in the line, `i` makes the search case-insensitive, and `c` asks for confirmation before each substitution.
- `count`: Number of lines to replace text in.

Here are some examples:

- Replace the first occurrence of ‘foo’ in the current line with ‘bar’:

```vim
:s/foo/bar/
```

- Replace all occurrences of ‘foo’ in the current line with ‘bar’:

```vim
:s/foo/bar/g
```

- Replace all occurrences of ‘foo’ in the entire file with ‘bar’:

```vim
:%s/foo/bar/g
```

- Replace all occurrences of ‘foo’ in the entire file with ‘bar’, asking for confirmation each time:

```vim
:%s/foo/bar/gc
```

[Remember to be in normal mode (press `Esc` key) before running these commands](https://linuxize.com/post/vim-find-replace/) [@FindReplaceVim2021]

⌂
<br>﹈<br>^1707633055906

﹇<br>
As of Feb. 10, 2024 10:28:19 PM, in the context of **Vim**, how do replace the first occurrences of ‘foo’ in the current line with ‘bar’?

#anki-card 

```vim
:s/foo/bar/
```

⌂
<br>﹈<br>^1707633055917

﹇<br>
As of Feb. 10, 2024 10:28:19 PM, in the context of **Vim**, how do replace all occurrences of ‘foo’ in the current line with ‘bar’?

#anki-card 

```vim
:s/foo/bar/g
```

⌂
<br>﹈<br>^1707633055922

﹇<br>
As of Feb. 10, 2024 10:28:19 PM, in the context of **Vim**, how do replace all occurrences of ‘foo’ in the current file with ‘bar’?

#anki-card 

```vim
:%s/foo/bar/g
```

⌂
<br>﹈<br>^1707633055927

﹇<br>
As of Feb. 10, 2024 10:28:19 PM, in the context of **Vim**, how do you replace all occurrences of ‘foo’ in the entire file with ‘bar’, asking for confirmation each time?

#anki-card 

```vim
:%s/foo/bar/gc
```

⌂
<br>﹈<br>^1707633055931


---

## :EiZoteroItem: Bibliography

---

> [!INFO]+ Notes
> **Next Notes**:
> 
