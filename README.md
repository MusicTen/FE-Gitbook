# MusicTen-知识拾遗

## gitbook发布到gh-pages分支

1. 在master主分支上，输入 `gitbook build` 命令，生成一个 `_book` 文件夹

   ```bash
   gitbook build
   ```

2. 剪切 `_book` 文件夹，切换到gh-pages分支，然后粘贴 `_book` 文件夹里的内容到gh-pages分支

   ```bash
   git checkout gh-pages
   ```

3. 删除远程gh-pages分支（可有可无，若4步上传出错，执行）

   ```bash
   git push origin --delete gh-pages
   ```

4. 上传gh-pages分支到远程仓库

   ```bash
   git push origin gh-pages
   ```

> window系统上起启动gitbook服务后， 如果本地文件发生更改，热加载会失败。
>
> 注意：**md文件命名**（不能中文）。命名不规范， 亲人两行泪

## GFM–GitHub Flavored Markdown

使用 markdown 写博客，写出的 markdown 文件尽最大可能保持其文档特性，即语法简洁容易理解，尽量不包含 github 不支持显示的语法。换句话说，就是尽量以 [GFM–GitHub Flavored Markdown](https://help.github.com/articles/github-flavored-markdown) 为标准。所以避免使用一切 Jekyll tag。

> Liquid是 `Shopify` 开发的简易灵活安全的标记语言。一个重要的应用场景就是Jekyll。Jekyll使用Liquid作为模板语言, 加入了一些标签和filter。

代码块通过加语法高亮更容易阅读，在栅栏式代码块基础之上，增加一个可选的语言标字符(如 ruby，C，C++，pyhon等等)，GFM通过此种方式来进行代码语法高亮

> GFM使用[Linguist](https://github.com/github/linguist)来检测语言进行语法高亮，可以参阅[YAML file](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml)来确定哪些关键字的语言被支持