

# 跨域

## 同源策略

同源策略限制的情况有以下三种：

1、Cookie、LocalStorage和 IndexDB 无法读取

2、DOM 和 Js对象无法获得

3、AJAX 请求不能发送

> 注意：对于像 img、iframe、script 等标签的 src 属性是特例，它们是可以访问非同源网站的资源的。

## 如何解决跨域问题

### cookie跨域处理

先举个简单的例子来说下遇到的问题，比如www.news.baidu.com和www.map.baidu.com两个网页一级域名相同，只是二级域名不同，被认为不同源，但是开发者希望登录信息cookie共享。

首先浏览器允许通过设置document.domain共享 Cookie。前端可以设置相同的document.domain，两个网页就可以共享Cookie了。

![img](https://image.520mwx.com/static/9c6c6c586eae06b2254fecaf4aa65022.png) 

另外，服务器也可以在设置Cookie的时候，指定Cookie的所属域名为一级域名，比如.baidu.com。这样的话，二级域名和三级域名不用做任何设置，都可以读取这个Cookie。

这种方式只适合主域名相同，但子域名不同的iframe跨域。那么不同窗口不同页面的跨域通讯如何处理？

HTML5为了解决这个问题，引入了一个全新的API：跨文档通信 API（Cross-document messaging）。这个API为window对象新增了一个window.postMessage方法，允许跨窗口通信，不论这两个窗口是否同源。

![img](https://image.520mwx.com/static/33e54047ae1fdcb58d91b9d44fcdbb42.png) 

### 请求跨域处理

开发过程中遇到最多的就是**请求跨域**。

浏览器对于 JavaScript 的同源策略的限制，例如 a.com 下面的 js 不能调用 b.com 中的 js 中的对象或数据，因为 a.com 和 b.com 是不同域，请求的 url 地址，必须与浏览器上的 url 地址处于同域上，也就是域名，端口，协议相同，这就是同源策略的保护。如果浏览器对 JavaScript 没有同源策略的保护，那么一些重要的机密网站将会很危险。

那么针对请求不能发送，这条同源策略的限制，有以下几个解决方案：

#### 1、JSONP

 JSONP是服务器与客户端跨源通信的常用方法。最大特点就是简单适用，老式浏览器全部支持，服务器改造非常小。上面讲到在HTML标签里，一些标签比如script、img这样的获取资源的标签是没有跨域限制的，利用这一点，我们可以这样干。缺点：只能用于get请求。

#### 2、CORS

CORS是跨源资源分享（Cross-Origin Resource Sharing）的缩写。它是W3C标准，是跨源AJAX请求的根本解决方法。相比JSONP，CORS允许任何类型的请求。在使用CORS来访问数据的时候，客户端不需要更改任何数据访问逻辑。所有的一切工作都是在服务端及浏览器之间自动完成的。服务端可以进行一些配置，其中Access-Control-Allow-Origin和Access-Control-Allow-Methods字段是必填的：

> Access-Control-Allow-Origin：它的值要么是请求时Origin字段的具体值，要么是一个*（表示接受任意域名的请求）；
>
> Access-Control-Allow-Methods：它的值是逗号分隔的一个具体的字符串或者*，表明服务器支持的所有跨域请求的方法

#### 3、架设服务器代理

浏览器请求同源服务器，再由后者（比如Nginx服务器）请求外部目标服务器。因为服务器与服务器之间通信是没有同源限制的。

#### 4、WebSocket

WebSocket是一种通信协议。该协议不实行同源政策，只要服务器支持，就可以通过它进行跨源通信。