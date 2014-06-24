Title: 域名绑定
url: domain

## 第一步，在网站设置中绑定

你需要在网站设置（网址类似http://yourdomain.com/admin）中，先设定需要绑定的域名，如下图：

![bind-domain-in-dashboard](/_image/2014-06-06/bind-domain-in-dashboard.png)

**如果你的网站文件夹是用域名作为名字的，则可以不用设置。**

如果绑定的是FarBox二级域名（形式如`***.farbox.com`）[^subdomain]，那么直接访问对应的域名就可以了（如果没有被别人使用的话）；如果是独立域名，则可以通过访问`yourdomain.com.park.farbox.net`来查看在FarBox服务器中是否已经生效[^domain-in-farbox]。




## 第二步，修改独立域名的DNS解析

> 你需要修改自己独立域名的解析，令其指向FarBox，网站才会和这个域名真正绑定起来。
> 如果你不使用独立域名，或者独立域名已经用NameServer的方式绑定过了，这步可以直接跳过。

### 方式1: 修改NameServer

这是最简单并且推荐的方式。请将域名的NameServers(域名注册商处设置)设置为`ns1.farbox.net` `ns2.farbox.net`（**不能与其它nameserver共存，将会解析失败！**）。

下面的图例是以Godaddy.com为例做的说明：

![Image Title](/_image/2014-06-06/nameserver.png)

你也可以使用`方式2`和`方式3`修改DNS的解析，但前提是你知道DNS解析的各类型要如何设置！

### 方式2: 修改DNS的CNAME

比如`yourdomain.com`需要绑定的，则在这个域名的DNS中创建一个CNAME记录，指向`yourdomain.com.park.farbox.net`。


### 方式3：修改A记录（不推荐）

> 尽量不要使用方式3，当我们IP发生变化的时候，这个记录就会无效掉。
> 同时，FarBox针对中国各省市的线路优化也将失效。
> 有些DNS托管商，可以设置根域名的CNAME，但会提示跟MX记录冲突；尽管试一下，如果设置后域名访问正常、邮件接收正常，便是可以的。


如果你的根域名无法使用CNAME指向，那么可以直接使用A记录。A记录的IP地址则需要查询`yourdomain.com.park.farbox.net`。 

通常以下两个（操作系统的）命令，能帮你找到对应的IP地址。
```
ping yourdomain.com.park.farbox.net
nslookup yourdomain.com.park.farbox.net
```



[^subdomain]: 3位长度以内的FarBox二级域名是系统保留域名; FarBox不允许无理由占用二级域名的行为，举个例子，假设你占用了100个FarBox二级域名又没有在实际使用，我们会拒绝再为你提供任何的服务; 另外需要注意，一些潜在的，拥有明显FarBox品牌特征的，请不要占用，比如blog.farbox.com, wiki.farbox.com, app.farbox.com .etc

[^domain-in-farbox]: 如果`yourdomain.com.park.farbox.net`的域名能访问，则说明在FarBox中是正常的，而`yourdomain.com`又无法访问，则是你自己的域名解析没有设置成功（这不是FarBox所能控制的）。

