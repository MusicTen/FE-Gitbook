# window 与 document 

window 对象的常用属性

- window.self 返回当前窗口的引用
- window.parent 返回当前窗体的父窗体对象
- window.top 返回当前窗体最顶层的父窗体的引用
- window.outerwidth 返回当前窗口的外部宽
- window.outerheight 返回当前窗口的外部高
- window.innerwidth 返回当前窗口的可显示区域宽
- window.innerheight 返回当前窗口的可显示区域高

提示：通过直接在 Chrome 控制台中输入 console.log(window) 可以查看到其所有的被当前浏览器支持的属性及值。

window 对象的常用方法

- window.prompt() 弹出一个输入提示框，若用户点击了“取消”则返回 null
- window.alert() 弹出一个警告框
- window.confirm() 弹出一个确认框
- window.close() 关闭当前浏览器窗口。 有些浏览器对此方法有限制。
- window.open(uri, [name], [features]) 打开一个浏览器窗口，显示指定的网页。name 属性值可以是“_blank”、“_self”、“_parent”、“_top”、任意指定的一个窗口名。
- window.blur() 指定当前窗口失去焦点
- window.focus() 指定当前窗口获得焦点
- window.showModalDialog(uri, [dataFromParent]) 打开一个“模态窗口”（打开的子窗口只要不关闭，其父窗口即无法获得焦点；且父子窗口间可以传递数据）

------

document 常见的属性

- body 提供对 `<body> `元素的直接访问。对于定义了框架集的文档，该属性引用最外层的 `<frameset>`。
- cookie 设置或返回与当前文档有关的所有 cookie。
- domain 返回当前文档的域名。
- lastModified 返回文档被最后修改的日期和时间。
- referrer 返回载入当前文档的文档的 URL。
- title 返回当前文档的标题。
- URL 返回当前文档的 URL。

document常见的方法

- write()：动态向页面写入内容
- createElement(Tag)：创建一个 HTML 标签对象
- getElementById(ID)：获得指定 id 的对象
- getElementsByName(Name)：获得之前 Name 的对象
- body.appendChild(oTag)：向 HTML 中插入元素对象