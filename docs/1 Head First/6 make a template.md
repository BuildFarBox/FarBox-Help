title: How to Make a Template?
url: how-to-make-a-template

## Write your first template directly!

### Preparation Work

> At the admin dashboard of a site, make sure the `Template Priority` is `Custom Template` now.

![Image Title](/_image/2014-06-10/template-priority.png)

> And you should have some artiles under your site now, then open FarBox Code Editor:

![Image Title](/_image/2014-06-07/code-editor.png)

### Create template files

> create index.jade( this one will control the contents of homepage), codes bellow:
```jade:n
html
    head
        title= site.title
        load("/template/style.scss")
    body
        for post in posts
            .post
                .content= post.content(1000)
                .title —— <{{post.title}}>
        .pager
            if pager.has_pre
                a.pre(href= pager.pre_url) <
            if pager.has_next
                a.next(href= pager.next_url) >

```

> Create style.scss (this one will control the styles of a page),  codes bellow:
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

### Start to change the codes!

> Now, you should also open other window (not IE browser) to view your own site...

1. modify index.jade, and set 1000 to 10 in line 8.
-  modify index.jade at line 9, change `<{{post.title}}>` to <Hello world. {{post.title}}>
-  modify style.scss at line 4, replace `color: #666;` with `color: red;`
- .etc

If you knew something about HTML/CSS, you will find `custom a template` is really simple and friendly; even you knew nothing about HTML/CSS, try to modify anything in the template file, the real page will be re-rendered or refreshed automatically in realtime.



## Feel interested, and want to learn more?

> We recommend you to do it follow the three steps bellow:

### Step 1, Find the Template Folder

**Assume your current site folder is `Dropbox/APPs/FarBox/MyBlog/`.**

The template files are under  `Dropbox/APPs/FarBox/MyBlog/template/`, if the folder not exists, create it first.

And `Dropbox/APPs/FarBox/MyBlog/template/index.jade` will be your homepage.

### Step 2, Download a Template Package

Maybe you should try our [default template](https://github.com/BuildFarBox/default-template) first.

And there are some [repos](https://github.com/BuildFarBox/) we host on Github. Of couse, you can also [Search](https://github.com/search?o=desc&q=farbox&ref=cmdform&s=updated&type=Repositories) other people's template packages.


After downloaded a template package, you need to put the template files into your `template` folder.


Here are some errors of location:
```
Dropbox/APPs/FarBox/MyBlog/template/index.jade --> correct

Dropbox/APPs/FarBox/MyBlog/template/Name/index.jade --> error
Dropbox/APPs/FarBox/MyBlog/template/Name/template/index.jade --> error
```


### Step 3, Know Some FarBox Template Syntax

```jade
head
	if site.title
		title= site.title
body
	for post in posts
		h1= post.title
```

Is this Template API Syntax beautiful?  Details refer here [FarBox Template Syntax](http://doc.farbox.com/read/template-syntax)。



