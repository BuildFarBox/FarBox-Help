Title: Bind Domains
url: domain

## Step 1, binding in site admin dashboard

You need to bind a domain in the site admin dashboard, ( the URL looks like http://yourdomain.com/admin):

![bind-domain-in-dashboard](/_image/2014-06-06/bind-domain-in-dashboard.png)

**If you used a domain as the name of your site folder, there is no need to setup again in the dashboard.**

If you binded a subdomain of FarBox ( looks like `***.farbox.com` )[^subdomain], just visiting it (if it was not occupied by others). If the doamin is an independent one, you can visiting `yourdomain.com.park.farbox.net` to check if it works in FarBox side [^domain-in-farbox].




## Step 2, modify the DNS records of your independent domain

> If the domain you binded is not an independent domain, or your domain was binded by modifying the NameServer, you can skip this step now.

### Option 1: Modify NameServer

The is the simplest and recommended way, please set the Nameservers of your domain at your registrant to.
`ns1.farbox.net` `ns2.farbox.net`（**There should be no other nameservers together, other ways it won't work!**）.

The image bellow, takes Godaddy.com as an example:

![Image Title](/_image/2014-06-06/nameserver.png)

You also can use `option 2` and `option 3` to modify your DNS records, but only if you knew how to set different types of DNS records.

### Option 2: Modify CNAME of DNS

If you want to bind `yourdomain.com`, then create a CNAME record whose value is `yourdomain.com.park.farbox.net`.


### Option 3: Modify A Record (not recommended)

> Avoid to use this solution if possible, when FarBox changes the IP, A record will fail to work.
> And the Network Optimization of FarBox does not work for A Record.

If your root domain can't use CNAME, you could use A Record instead. The IP of A Record is related to `yourdomain.com.park.farbox.net`.


Usually, these two terminal commands of OS can help you to find the IP for A Record.
```
ping yourdomain.com.park.farbox.net
nslookup yourdomain.com.park.farbox.net
```



[^subdomain]: We offer free subdomains of FarBox, like `***.farbox.com`, the max-length is 3. To occupy a subdomain without a reasonable reason is not allowed. For example, if you occupy a hundred subdomains, we would suspend your account. And do not try to occupy the subdomains that related to the brand of FarBox, like blog.farbox.com, wiki.farbox.com, app.farbox.com .etc

[^domain-in-farbox]: If the `yourdomain.com.park.farbox.net` is accessible, but the `yourdomain.com` is not, it means your DNS records failed (this is out of the control of FarBox).

