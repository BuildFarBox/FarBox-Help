Title: Rules for Writting
url: basic-writting
toc: yes

## Basic Description

### APPs for Writting

- FarBox Web Editor: After logged in at www.farbox.com, you can find the entrance or go http://yourdomain.com/admin/editor directly；this is a very simple Editor。
- FarBox Desktop Editor: [click and download it](https://www.farbox.com/service/download-editor)（**recommend！**），supports Win/Mac, besides writing and logging, it also can export a whole folder into a PDF document.
- Other APPs (for Apple): [Mou](http://mouapp.com/), [iA Writer](http://www.iawriter.com/), [Byword](http://bywordapp.com)

> Like iA Writer and Byword, they are across-platform APPs, there is also APPs for iPhone and iPad, and supports Dropbox too (means you can edit/save a document into FarBox directly).
> If you are using other applications, just save your posts into the directory of FarBox, it just works!



### Basic Rules

- filename is the title of post
- file content is the body of post

> The suffix of the filename of a post, should be one of `.txt .md .markdown .mk`.  

### Insert an Image

If you are using FarBox Editor, just drag an image into the textarea, that's all.

> You also can use Markdown syntax to insert it directly, `![](<image_path>)`, and the image_path is a relative path to the site directory, like `/_image/your_photo.jpg`.


### Modify Propeties

> FarBox is using a [Config Syntax](http://doc.farbox.com/read/syntax-of-configs) to extend the properties of a document. 

Below is a brief introduction to the rules for a post.

If a post looks like:
```
Date: 2012-10-25 12:22
Title: I am a title
Tags: tag1, tag2
Status: draft

this is text body...
```

- Date is the publish date for post
- Title is the title of post (if you don't like to use the filename by default)
- Tags can set the tags of post
- Status is the status of your post, default value (if not declared) is `public`. Usually, the post list of your site contains the posts whose status is `public`.

> If you want to learn more about the properties/configs of a post, please check [>Configs of Post](http://doc.farbox.com/read/post-configs)

## About Markdown

FarBox supports [Markdown](http://daringfireball.net/projects/markdown/syntax) (if necessary, you can disable this feature in the site admin dashboard), usually, you just write, and no need to know how Markdown works.

The orignal Markdown syntax ask for tow line-breaks to break a line, bug FarBox won't follow this rule, except the suffix of your post is **.mk**.

In most cases of format errors/mistakes when using Markdown, you can fix it by **add (or cut) one more space/line-break**.


> Bellow is some special Markdown syntax for FarBox:

### Table
A simple table looks like this:

```
First Header | Second Header | Third Header
------------ | ------------- | ------------
Content Cell | Content Cell  | Content Cell
Content Cell | Content Cell  | Content Cell
```


### Footnotes

    This is emphatically [^1]
    Something else [^key2].
    EOF
    
    [^1]: emphatically: some thing here
    [^key2]: footnote for key2



### Code Highlight

Declare your code language, then the code will be highlighted; the code block Starts (and ends) with a line containing 3 \` characters.

\`\`\`python 
codes
\`\`\`

If you want to show the lines of code, add `:n` at the end of the code language.

\`\`\`python:n
codes
\`\`\`

> We are using the [Pygments](http://pygments.org/docs/styles/) package to highlight code and the style is controled by CSS. There are some common kinds of [Pygments Style](/pygments.html).

### Insert a Gist

In a separate line ，\`gist gist_id\`. The character \` is necessity.

Tip: sometimes, you should set the `word-break` to `normal` in your customed CSS style to avoid to break the gist styles.

```css
.gist{
    word-break: normal;
}
```


## Mathjax

\`\`\`mathjax
your mathjax code.
\`\`\`

Make sure, you already understand how Mathjax works, and in your site admin dashbord, the `Use MathJax` is set to `On` or `yes`.









