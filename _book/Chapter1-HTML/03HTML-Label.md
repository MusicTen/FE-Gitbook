# HTML标签

### HTML 语义化的理解

- 语义化：指使用恰当语义的 H5标签，如 `<header> `代表头部，`<article> `代表正文等
- 好处：增强了可读性（更容易让屏幕阅读器读出网页内容）、有利于SEO优化（更容易被搜索引擎收录）

| 标签     | 作用                                              |
| -------- | ------------------------------------------------- |
| `<hr />` | 在页面显示一条横线（没有语义） // Horizontal Rule |
| `<br />` | 换行 // break                                     |
| `&nbsp;` | 空格                                              |
| `&lt;`   | <                                                 |
| `&gt;`   | >                                                 |

| 加粗       | 倾斜   | 下划线  | 删除线  | 是否有语义   |
| ---------- | ------ | ------- | ------- | ------------ |
| `<b>`      | `<i>`  | `<u>`   | `<s>`   | 无           |
| `<strong>` | `<em>` | `<ins>` | `<del>` | 强调加强语气 |

### `<!doctype html>`

​	DTD文档声明头，处在文档最前面，告知浏览器文档使用哪种规范解析

### `<head>`

​	定义文档头部，包含`<meta>`、`<title>`、`<link>`、`<script>`、`<style>`、`<base>`

### `<meta>`

> meta标签作用：描述网页元信息

**常用的 meta 标签**

- charset，用于描述 HTML 文档的编码形式

```html
<meta charset="UTF-8">
```

> UTF-8 > GBK > GB2312 (最常见的三种字符集)

- http-equiv，相当于 HTTP 的文件头作用，比如下面的代码就可以设置 HTTP 的缓存过期日期

```html
<meta http-equiv="expires" content="Wed, 20 Jun 2019 22:33:00 GMT"＞
```

- viewport，控制视口的大小和比例

```html
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
```

### `<base>`

​	可以为页面所有a标签设置跳转方式

```html
<base target="_blank" />
```

### `<a>`

> 超链接/锚链接 // Anchor

1. 可以不跳转（跳转到当前页面）`href="#"`

2. 可以跳转到其他页面

3. 可以在当前页面定位

   （1）设置a标签的`href="#id"`

   ```html
   <a href="#mubiao">点我定位</a>
   ```

   （2）在页面的指定位置加入一个目标标签（可以是任意标签），必须设置id

   ```html
   <div id="mubiao">我是目标标签</div>
   ```

4. 可以在跳转页面定位

5. 可以进行下载（强烈不推荐使用，安全性低）

a标签的属性：

- href：a标签跳转的目标地址
- target：`_blank`保留原页面，新打开一个tab页面；`_self`当前页面跳转

### `<table>`

```html
<table border="1">
    <caption>表格标题</caption>
    <tr>
        <th colspan="2">天气</th> // 跨列合并
    </tr>
    <tr>
        <th>今天</th>
        <td>多云</td>
    </tr>
    <tr>
        <th>明天</th>
        <td>小雨</td>
    </tr>
</table>
<table border="1">
    <caption>表格标题</caption>
    <tr>
        <th rowspan="2">天气</th> // 跨行合并
        <th>今天</th>
        <td>多云</td>
    </tr>
    <tr>
        <th>明天</th>
        <td>小雨</td>
    </tr>
</table>
```

> cellspping：单元内容与边框之间空白；cellspacing：单元格之间空白。（H5 均不支持）

| 属性                         | 作用                                                         |
| ---------------------------- | ------------------------------------------------------------ |
| `border-collapse: collapse;` | （合并边框）细线表格，作用`<table>`                          |
| vertical-align               | 设置行内元素的垂直对齐方式<br />在表单元格中，这个属性会设置单元格框中的单元格内容的对齐方式 |
| text-align                   | 将块级标签以及单元格里面的内容进行相应的对齐                 |

### `<form>`

​	表单：用于收集用户信息

```html
<form action="提交地址" method="get/post" enctype="multipart/form-data（允许上传文件）">
    <label type="text" >输入框</label>
    <input name="" type="text" size="22" /><br />
    <label type="checkbox">多选复选框</label>
    <input name="" type="checkbox" value="" /><br />
    <label type="radio">单选框</label>
    <input name="" type="radio" value="" /><br />
    <label type="submit">按钮</label>
    <input name="" type="submit" value="提交" />
</form>
```

| 属性                   | 作用                              |
| ---------------------- | --------------------------------- |
| `outline-style: none;` | 去除 input 获取焦点时的蓝色外边框 |
| `input-style: none;`   | 清除 input 默认的轮廓             |
| `resize: none;`        | 禁止 areatext 改变大小            |

**H5新增新标签**

- `<fieldset>`：可以将表单内的相关元素分组（有边框）

- `<legend>`：为fieldset定义标题，必须是fieldset的子元素

```html
<form>
    <fieldset>
        <legend>登录</legend>
        姓名: <input type="text" name="" />
        密码: <input type="password" name="" />
    </fieldset>
</form>
// fieldset有个form属性可以规定fieldset所属的表单，其值是form表单的id（可写在form表单外）
```

