# MusicTen-知识拾遗

使用 markdown 写博客，坚持写出的 markdown 文件尽最大可能保持自文档特性，即语法简洁容易理解，尽量不包含 github 不支持显示的语法。换句话说，就是尽量以 [GFM–GitHub Flavored Markdown](https://help.github.com/articles/github-flavored-markdown) 为标准。所以我避免使用一切 Jekyll tag，除了数学公式（github 现在还不支持常见的以$符识别 tex 的特性，但数学公式实在不可避免）。

代码块通过加语法高亮更容易阅读，在栅栏式代码块基础之上，增加一个可选的语言标字符(如 ruby,C,C++,pyhon等等)，GFM通过此种方式来进行代码语法高亮

> GFM使用[Linguist](https://github.com/github/linguist)来检测语言进行语法高亮，可以参阅[YAML file](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml)来确定哪些关键字的语言被支持