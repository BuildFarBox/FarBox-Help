title: 如何自定义模板？
url: how-to-make-a-template

## 直接开始写第一个模板吧！

### 准备工作

> 在网站的后台管理中，确保`模板的优先级`设置为了`自定义模板`。

![Image Title](/_image/2014-06-10/template-priority.png)

> 保证网站内是有文章的（不然模板看起来没有效果），然后进入代码编辑器，如下图所示：

![Image Title](/_image/2014-06-07/code-editor.png)

### 创建模板文件

> 创建index.jade(控制页面的内容)，源码如下：
```jade:n
html
    head
        title= site.title
        load("/template/style.scss")
    body
        for post in posts
            .post
                .content= post.content(1000)
                .title ——《{{post.title}}》
        .pager
            if pager.has_pre
                a.pre(href= pager.pre_url) <
            if pager.has_next
                a.next(href= pager.next_url) >

```

> 创建style.scss(控制页面的风格)，源码如下：
```scss:n
body {
    font: normal 14px Arial, Helvetice, Verdana, sans-serif;
    line-height: 1.9em;
    color: #666;
    width: 600px;
    margin: 0 auto;
    padding-top: 50px;
}

.post {
    margin-bottom: 130px;
    .title {
        margin-top: 30px;
        text-align: right;
    }
}

.pager {
    a {
        text-decoration: none;
        color: #ddd;
        font-size: 72px;
        &:hover {
            color: #111;
        }
    }
}
```

### 开始改代码吧！

> 此时，你应该在另外的浏览器（非IE）窗口打开了自己的网站...

1. 修改index.jade的第8行将1000改为10试试。
- 修改index.jade的第9行的`《{{post.title}}》`为《Hello world. {{post.title}}》
- 修改style.scss的第4行的`color: #666;`为`color: red;`
- .etc

如果你对HTML/CSS有一定的了解，就会发现在FarBox上自定义模板非常的简单与友好；即使不了解HTML/CSS，也可以猜测着修改一些地方，页面会随着修改而自动刷新，这样就知道自己改后的效果了！


## 对自定义模板感兴趣了，需要进一步了解？

> 我们建议可以按照下面三个步骤，进一步了解FarBox的模板系统。

### 第一步，了解模板目录所在的位置

**假设你现在的网站目录为`Dropbox/应用/FarBox/MyBlog/`**

模板页面则要放置于`Dropbox/应用/FarBox/MyBlog/template/`的目录下， 没有这个目录，则需要创建一个。

那么`Dropbox/应用/FarBox/MyBlog/template/index.html`的内容，将会是你的网站首页。


### 第二步，下载网站模板源码

我们建议可以先下载[默认模板的代码](https://github.com/BuildFarBox/default-template)。

也可以到我们团队托管在GitHub的[代码库](https://github.com/BuildFarBox/)中找, 或者直接[搜索](https://github.com/search?o=desc&q=farbox&ref=cmdform&s=updated&type=Repositories)其他人的模板代码。

然后，把需要的模板文件放在自己网站的`template`目录内。

几种常见的位置错误，举例说明：
```
Dropbox/应用/FarBox/MyBlog/template/index.html --> 正确的

如果出现以下路径，则是错误的:
Dropbox/应用/FarBox/MyBlog/template/Name/index.html --> 错误的
Dropbox/应用/FarBox/MyBlog/template/Name/template/index.html --> 错误的
```


### 第三步，了解FarBox模板的基本语法

```jade
head
	if site.title
		title= site.title
body
	for post in posts
		h1= post.title
```

这样的API语法是不是很漂亮? 具体可以了解[FarBox模板语法](http://doc.farbox.com/read/template-syntax)。



