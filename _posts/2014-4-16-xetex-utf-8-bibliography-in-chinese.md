---
layout: post
title: XeTeX+UTF-8中文参考文献排序
categories: [奇技淫巧]
tags: [TeX]
---

人文社科领域通常采用著者—出版年（Author-Year）方式引用文献，对于文后参考文献列表，英文文献按作者姓氏字母排序，中文文献按照作者姓名拼音排序。[hooklee](http://www.hooklee.com/) 曾开发了一个 BibTeX 中文化工具「fixbbl」，用于参考文献按拼音、笔顺和笔画数排序。但是这个程序上次更新已经是近十年前了，与当前更加常用的 UTF-8 编码不兼容。

以参考文献样式 [GBT7714-2005.bst](http://bbs.ctex.org/forum.php?mod=viewthread&tid=33591) 为例，传统的编译步骤是`latex -> fixbbl -> 修改 .bbl 文件 -> latex -> latex`，但是这种方法默认支持 GBK 编码，所以需要在编译过程中将 UTF-8 临时转为 GBK，具体而言就是`xelatex -> UTF-8 转 GBK -> fixbbl -> 修改 .bbl 文件 -> GBK 转 UTF-8 -> xelatex -> xelatex`。

---

在 Windows 下实现这个操作，需要的程序包括 [fixbbl](http://www.hooklee.com/default.asp?t=TeX%2FLaTeX)，[replace_fs](http://www.hooklee.com/default.asp?t=TeX%2FLaTeX)，[LibIconv](http://gnuwin32.sourceforge.net/packages/libiconv.htm) 和 [GetText](http://gnuwin32.sourceforge.net/packages/gettext.htm)。把以下文件解压到同一个目录下：

	GBK2py.inf			iconv.exe
	GBT7714-2005AYLang-UTF8.bst	libcharset1.dll
	fixbbl.bat			libiconv2.dll
	fixbbl.cfg			libintl3.dll
	fixbbl.exe			replace_fs.exe

以编译 test.tex 和 test.bib 为例，依次运行以下命令，或者存为 .bat 文件运行，就可以得到中文文献按拼音排序的结果了。示例文件可以在[这里](http://vdisk.weibo.com/s/igDHU8nU4ZDO)下载。


	xelatex test
	ren GBT7714-2005AYLang-UTF8.bst GBT7714-2005AYLang-UTF8.bst8
	ren test.bib test.bib8
	ren test.aux test.aux8
	iconv -f UTF-8 -t GBK GBT7714-2005AYLang-UTF8.bst8 > GBT7714-2005AYLang-UTF8.bst
	iconv -f UTF-8 -t GBK test.bib8 > test.bib
	iconv -f UTF-8 -t GBK test.aux8 > test.aux
	fixbbl test -sort=py -cjk
	replace_fs test.bbl ]//. ]//
	ren GBT7714-2005AYLang-UTF8.bst GBT7714-2005AYLang-UTF8.bstg
	ren test.bib test.bibg
	ren test.aux test.auxg
	ren test.bbl test.bblg
	iconv -f GBK -t UTF-8 GBT7714-2005AYLang-UTF8.bstg > GBT7714-2005AYLang-UTF8.bst
	iconv -f GBK -t UTF-8 test.bibg > test.bib
	iconv -f GBK -t UTF-8 test.auxg > test.aux
	iconv -f GBK -t UTF-8 test.bblg > test.bbl
	xelatex test
	xelatex test
	del GBT7714-2005AYLang-UTF8.bst8
	del GBT7714-2005AYLang-UTF8.bstg
	del test.bib8
	del test.bibg
	del test.aux?
	del test.bbl?
	del test.bbl.bak
	del test.blg
	del test.log

---
对于 OS X 而言，由于无法使用 fixbbl 程序，所以只有一个妥协的方案：由于 GBK 编码中来自 GB 2312-80 的部分，即6000多个常用汉字，是按照拼音排序的，所以按 GBK 编码排序可以保证大部分文献排序正确，对于少数漏网之鱼就只能手动修改 .bbl 文件了。

在 OS X 下实现这个操作不需要额外的程序，依次运行以下命令，或者存为 .sh 文件运行，就可以得到中文文献按（伪）拼音排序的结果了。示例文件可以在[这里](http://vdisk.weibo.com/s/igDHU8nU4ZBS)下载。

	xelatex test
	mv GBT7714-2005AYLang-UTF8.bst GBT7714-2005AYLang-UTF8.bst8
	mv test.bib test.bib8
	mv test.aux test.aux8
	iconv -f UTF-8 -t GBK < GBT7714-2005AYLang-UTF8.bst8 > GBT7714-2005AYLang-UTF8.bst
	iconv -f UTF-8 -t GBK < test.bib8 > test.bib
	iconv -f UTF-8 -t GBK < test.aux8 > test.aux
	bibtex test
	mv GBT7714-2005AYLang-UTF8.bst GBT7714-2005AYLang-UTF8.bstg
	mv test.bib test.bibg
	mv test.aux test.auxg
	mv test.bbl test.bblg
	iconv -f GBK -t UTF-8 < GBT7714-2005AYLang-UTF8.bstg > GBT7714-2005AYLang-UTF8.bst
	iconv -f GBK -t UTF-8 < test.bibg > test.bib
	iconv -f GBK -t UTF-8 < test.auxg > test.aux
	iconv -f GBK -t UTF-8 < test.bblg > test.bbl
	sed -i '' 's/\]\/\/./\]\/\//g' test.bbl
	xelatex test
	xelatex test
	rm GBT7714-2005AYLang-UTF8.bst?
	rm test.bib?
	rm test.aux
	rm test.aux?
	rm test.bbl
	rm test.bbl?
	rm test.blg
	rm test.log

其中，`sed`命令这一行是取代了 replace_fs 的功能，只在使用 GBT7714-2005.bst 时有用。

---
P.S. GBT7714-2005.bst 中似乎有一处小 bug，编译出来的文档中，（某某某 等，2014）这里的「等」前多了一个空格。解决方法是把 GBT7714-2005AYLang-UTF8.bst 文件第2991行的`{ pop$ "~等" * }`改为`{ pop$ "等" * }`。
