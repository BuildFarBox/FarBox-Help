Title: 写作规则
url: basic-writting
toc: yes

## 基本说明

### 写作软件

- FarBox Web Editor: 通过www.farbox.com登录后的页面进入，或者http://yourdomain.com/admin/editor进入；这是一个比较简洁的Editor。
- FarBox桌面Editor: [点击此处下载](https://www.farbox.com/service/download-editor)（**推荐！**），目前支持Win/Mac，除了日常写作记录外，还能将一个文件夹导出为PDF的电子书。
- 其它APP（苹果系）: [Mou](http://mouapp.com/), [iA Writer](http://www.iawriter.com/), [Byword](http://bywordapp.com)

> 像iA Writer和Byword是跨平台的，有iPhone/iPad端，并且支持Dropbox（也就是可以直接编辑、保存到FarBox的网站里）。
> 其它写作软件，只要把自己的文章保存到FarBox的对应网站里，效果也是一样的。



### 基本规则

- 文件名即文章的标题
- 文件内容，即文章正文

> 文章的文件名，其后缀支持.txt .md .markdown .mk四种格式。  

### 插入图片

在FarBox Editor中，你只需要把图片拖入文本区域就可以了。

> 你也可以使用Markdown的语法`![](<image_path>)`直接插入图片，图片为相对网站目录的路径，比如`/_image/your_photo.jpg`。


### 修改文章的属性

> FarBox使用统一的[配置语法](http://doc.farbox.com/read/syntax-of-configs)来实现文档的属性扩展, 下面将对一些常用的属性做简单介绍。

如果一篇文章是如下格式的：
```
Date: 2012-10-25 12:22
Title: 我是文章的标题
Tags: 标签1, 标签2
Status: draft

然后开始写正文...
```

- Date可以设置文章发表时间
- Title可以设置文章的标题（如果不想用文件名做标题）
- Tags可以设置文章的标签。如果标签中没有连词的，直接使用空格；如果有连词的话，使用英文状态下的`,`进行分割即可
- Status表示文章的状态，默认的是`public`。日志列表内输出的一般都是`public`属性的文章，像上面示例中`draft`则表示不在网站里出现。

> 这里仅对主要的几个属性进行了说明，如果需要了解更多，请访问[>日志的属性](http://doc.farbox.com/read/post-configs)

## 关于Markdown

FarBox默认支持[Markdown](http://wowubuntu.com/markdown/)的语法（也可以在网站后台中禁止Markdown）, 一般情况下，你不了解Markdown也能正常使用。

一般的Markdown格式是要求两个换行才算是真正视觉上的换行，而在FarBox则不遵循这个规则（文件后缀名为**.mk**的除外）。

多数情况下，在使用Markdown格式时，出现的格式问题可以通过这样的方式解决：**多（或者少）一个空格、换行**。

> 以下特性是FarBox特殊支持的Markdown语法：

### 表格
一个表格看起来如下所示:

```
First Header | Second Header | Third Header
------------ | ------------- | ------------
Content Cell | Content Cell  | Content Cell
Content Cell | Content Cell  | Content Cell
```


### 脚注

    This is emphatically [^1]
    Something else [^key2].
    EOF
    
    [^1]: emphatically: 坚决地，着重地，强调地（~ deny 坚决否定）
    [^key2]: key2的注释



### 代码高亮

如果声明代码语言的，会进行代码高亮的处理；代码块需要分别用三个**反引号**（一般在键盘`1`键的左侧）包裹。

\`\`\`python 
codes
\`\`\`

如果语言后面多一个`:n`，则会显示代码的行号。

\`\`\`python:n
codes
\`\`\`

> 代码的高亮的具体样式是由CSS控制的，由[Pygments](http://pygments.org/docs/styles/)生成。你可以访问[Pygments Styles](/pygments.html)查看常见的几种风格。

### 插入gist

单独一行，\`gist gist_id\`就可以了。反引号\`是必须的，以避免跟其它普通文字产生潜在的冲突。


### Mathjax

\`\`\`mathjax
your mathjax codes.
\`\`\`

这样的写法，会被解析为Mathjax能够处理的脚本。但前提你已经知道Mathjax是如何运作的，或者直接在网站的后台管理中另外`启用数学公式`。








