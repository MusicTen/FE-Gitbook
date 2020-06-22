# WEB API

## API是什么？

Application Programming Interface：应用程序编程接口。是一些预先定义的函数，通俗的理解就是一些方法。

## WebAPI是什么？

**浏览器**提供的一套操作浏览器功能和页面元素的API。

此处的Web API特指浏览器提供的一些方法。可分为两个部分：

1. BOM（浏览器对象模型）
2. DOM（文档对象模型）

## 1、DOM

### DOM的概念

文档对象模型（Document Object Model，简称DOM），是[W3C](http://baike.baidu.com/item/W3C)组织推荐的处理可扩展标志语言的标准编程接口。在网页上，组织页面（或文档）的对象被组织在一个树形结构中，用来表示文档中对象的标准模型就称为DOM。

- Document 对象

- Element 对象

  - element.offsetWidth   返回元素的宽度
  - element.offsetHeight   返回元素的高度
  - element.style   设置或返回元素的 style 属性
  - element.appendChild()   向元素添加新的子节点，作为最后一个子节点

- Attribute 对象

- Event 对象

  - onclick   当用户点击某个对象时调用的事件句柄

  - onerror   在加载文档或图像时发生错误
  - onload   一个页面或一幅图像完成加载
  - onresize   窗口或框架被重新调整大小
  - onmousedown   鼠标按钮被按下

#### Document 对象

##### Document 对象属性

| 属性                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| body                                                         | 提供对` <body> `元素的直接访问。对于定义了框架集的文档，该属性引用最外层的 `<frameset>` |
| [cookie](https://www.w3school.com.cn/jsref/prop_doc_cookie.asp) | 设置或返回与当前文档有关的所有 cookie                        |
| [domain](https://www.w3school.com.cn/jsref/prop_doc_domain.asp) | 返回当前文档的域名                                           |
| [referrer](https://www.w3school.com.cn/jsref/prop_doc_referrer.asp) | 返回载入当前文档的文档的 URL                                 |
| [title](https://www.w3school.com.cn/jsref/prop_doc_title.asp) | 返回当前文档的标题                                           |
| [URL](https://www.w3school.com.cn/jsref/prop_doc_url.asp)    | 返回当前文档的 URL                                           |

##### Document 对象方法

| 方法                                                         | 描述                                                      |
| :----------------------------------------------------------- | :-------------------------------------------------------- |
| [close()](https://www.w3school.com.cn/jsref/met_doc_close.asp) | 关闭用 document.open() 方法打开的输出流，并显示选定的数据 |
| [getElementById()](https://www.w3school.com.cn/jsref/met_doc_getelementbyid.asp) | 返回对拥有指定 id 的第一个对象的引用                      |
| [getElementsByName()](https://www.w3school.com.cn/jsref/met_doc_getelementsbyname.asp) | 返回带有指定名称的对象集合                                |
| [getElementsByTagName()](https://www.w3school.com.cn/jsref/met_doc_getelementsbytagname.asp) | 返回带有指定标签名的对象集合                              |
| [open()](https://www.w3school.com.cn/jsref/met_doc_open.asp) | 打开一个页面                                              |
| [write()](https://www.w3school.com.cn/jsref/met_doc_write.asp) | 向文档写 HTML 表达式 或 JavaScript 代码                   |

## 2、BOM

### BOM的概念

BOM(Browser Object Model) 是指浏览器对象模型，浏览器对象模型提供了独立于内容的、可以与浏览器窗口进行互动的对象结构。BOM由多个对象组成，其中代表**浏览器窗口的Window对象是BOM的顶层对象，其他对象都是该对象的子对象**。

### BOM顶级对象之window

调用window下的属性和方法时，可以省略window

- innerWidth 和 innerHeight 属性

- history 对象（用户(在浏览器窗口中)访问过的 URL） // 方法：

  - back( )    加载 history 列表中的前一个 URL

  - forward( )    加载 history 列表中的下一个 URL

  - go( )    加载 history 列表中的某个具体页面

- navigator 对象（包含有关浏览器的信息） // 常用属性：
  - userAgent    判断用户浏览器的类型
  - platform    判断浏览器所在的操作系统和平台类型

- location 对象（包含当前URL信息） // 常用属性：
  - href    设置或返回完整的URL
  - host    设置或返回主机名和当前 URL 的端口号
  - search    设置或返回从问号 (?) 开始的 URL（查询部分）
  - hash    设置或返回从井号 (#) 开始的 URL（锚）
  - port    设置或返回当前URL的端口号

- screen 对象 // 常用属性：
  - width  返回显示器屏幕的宽度
  - height  返回显示器屏幕的高度

- 三种对话框（模态框）
  - alert()  警告框，只有一个按钮“确定”无返回值
  - confirm()  确认框，有确定和取消两个按钮，用户点击确认返回值为 true，点击取消返回 false
  - prompt()  提示框，返回输入的消息，用户点击确认，返回值为输入的值，点击取消返回 null