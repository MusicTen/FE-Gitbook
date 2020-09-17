# iframe

## 父页面向iframe子页面传递参数

父页面:

```html
<iframe src="video.html?params=123" width="100%" height="400" id="son" style="border: none; overflow:hidden" scrolling="no" link="http://www.baidu.com/"></iframe>
```

子页面:

```javascript
// 方法一：
var videoUrl = parent.window.document.getElementsById("son").getAttribute('link')
// 方法二：
var params = window.location.search // 获取查询字符串
```

## 同域 iframe 父子间传值

- 父页面调用子页面方法：`iframe.window.childMethod()`
- 子页面调用父页面方法：`parent.window.parentMethod()`

## 跨域 iframe 父子间传值

父页面：

```javascript
// 主动向子页面广播
let iframe = document.getElementById('son')
iframe.contentWindow.postMessage('父传子参数', '*')
// 监听子页面传来的值
window.addEventListener('message', function(e) {
    console.log("子页面参数：", e.data)
}, false)
```

子页面：

```javascript
// 主动向父页面广播
window.parent.postMessage('子传父参数', '*')
// 监听父页面传来的值
window.addEventListener('message', function(e) {
    console.log("父页面参数：", e.data)
}, false)
```

