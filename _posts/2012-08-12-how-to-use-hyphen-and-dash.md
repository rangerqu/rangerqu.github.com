---
layout: post
title: 英文标点连字号（hyphen）与连接号（dash）的使用方法
categories: [奇技淫巧]
tags: [English, productivity]
---

英文标点中有一些很容易弄混淆的符号，例如「-」、「–」和「—」，以前一直没有注意到其中的区别，直到写英文论文的时候才知道这三个符号有着严格的区分。

在英文中，这三个符号分别叫做 hyphen (-)、en dash (–) 和 em dash (—)，下面分别介绍一下这三个符号的使用方法：

# Hyphen (-)

Hyphen 就是连字号，主要用在以下几种情况：

1. 行末单词换行，例如
	- We, therefore, the represen-
	- tatives of the United States
	- of America…
1. 连接前缀与后缀，例如
	- co-worker
	- anti-intellectual
1. 连接复合词的各个组成部分，例如
	- 28-year-old woman
1. 分隔数字，例如
	- Tel: 585-362-4115
	- ISBN: 7-80087-535-0

# En dash (–)

En dash 是连接号，其长度等于大写字母 N，是 em dash 的一半，主要用在以下几种情况：

1. 连接数字表示起止范围，相当于中文里的「～」，例如
	- June–July 1967
	- 1:00–2:00 p.m.
	- pp. 38–55
	- President Jimmy Carter (1977–81)
1. 表示两者之间的关系和联系，相当于中文里的「－」，例如
	- The Supreme Court voted 5–4 to uphold the decision.
	- Boston–Hartford route
	- mother–daughter relationship
	- The Glass–Steagall Act
1. 在复合词构成的形容词定语中替代 hyphen，例如
	- pre–Civil War era
	- Pulitzer Prize–winning novel
	- public-school–private-school rivalries
	- New York–London flight

在使用 en dash 时要注意，其前后都不留空格，除非是不留空格影响美观的时候，例如用「12 June – 3 July」替代「12 June–3 July」。

此外，由于 en dash 的长度通常与加号（+）一样，所有有的时候也被用来替代减号（−），但实际上 en dash 与减号是不同的。

# Em dash (—)

Em dash 的长度等于大写字母 M，使用方法与中文的破折号（——）类似， 主要用在以下几种情况：

1. 替代逗号，将一个特定的概念从一个句子的主要从句中分离出来，例如
	- Sometimes writing for money—rather than for art or pleasure—is really quite enjoyable.
1. 分隔一个插入的想法或从句，例如
	- I can’t believe how pedantic Ken is about writing—I mean, doesn’t he have anything better to do?
1. 表示对话被打断，例如
	- “I reached in and pulled the spray can out of my pants—”
	- “In front of the police?”

在使用 em dash 时也要注意，其前后都不留空格。

另外，还有 2-em dash 和 3-em dash 两种用法：

## 2-em dash

2-em dash 即两个 em dash 连写，主要用于：

1. 表示在单词中省略了字母，例如
	- Mr. H—— and Mr. S—— entered into a legal agreement.
1. 表示在句子中省略了单词，这时前面需要加空格，例如
	- I distinctly heard him say, “Go away or I’ll ——”.

## 3-em dash

3-em dash 即三个 em dash 连写，主要用于：

1. 表示在句子中省略了单词，与 2-em dash 的第二种用法相同
1. 在参考文献目录中，如果紧接着的条目作者相同时用以省略，例如
	- Acemoglu, Daron, 1999. “Patterns of Skill Premia” NBER Working Paper No. 7018.
	- ———, 2001. “Directed Technical Change”, NBER Working Paper No. 8287.

那么，如何在电脑上输入这几种符号呢？

# Hyphen (-)

Hyphen 的 Unicode 编码是 U+2010，在 MS Word 里可以先输入 2010 再按 `Alt + X`。

不过在 ASCII 编码系统中，hyphen 被编为45号字符「hyphen-minus」，也就是我们电脑键盘上 `0` 和 `=` 之间的那个 `-` 。在通常情况下我们直接使用这个符号就可以了。

# En dash (–)

En dash 的 Unicode 编码是 U+2013，在 MS Word 里可以先输入 2013 再按 `Alt + X`，更简便的方法是利用 MS Word 的自动更正功能：按空格，按两下 `-` ，再按空格，例如输入 `this is -- a test` ，将转换为「this is – a test」（当然，要注意 en dash 前后一般是不留空格的）。

En dash 在 Windows 里可以用 `Alt + 0150` （即按下 `Alt` 键的同时依次按下 0150）来输入，在 Mac 里可以用 `⌥ + -` 来输入，在 TeX 里可以用 `--` 输入，在 HTML 里可以用 `&ndash;` 来输入。

# Em dash (—)

Em dash 的 Unicode 编码是 U+2014，在 MS Word 里可以先输入 2014 再按 `Alt + X`，更简便的方法是利用 MS Word 的自动更正功能：不加空格，直接按两下 `-`，例如

输入 `this is--a test` ，将转换为「this is—a test」

Em dash 在 Windows 里可以用 `Alt + 0151` 来输入，在 Mac 里可以用 `⌥ + ⇧ + -` 来输入，在 TeX 里可以用 `---` 输入，在 HTML 里可以用 `&mdash;` 来输入。

# Minus sign (−)

减号的 Unicode 编码是 U+2212，在 MS Word 里可以先输入 2212 再按 `Alt + X`。

减号在 TeX 里可以用 `$-$` 输入，在 HTML 里可以用 `&minus;` 来输入。