---
layout: post
title: "apache反向代理配置"
description: "apache反向代理配置"
category: Technology
tags: [technology,apache]
modified: 2013-06-30
image:
  feature: zunyi.jpg
comments: true
share: true
---

##配置示例：

{% highlight ruby linenos %}
<VirtualHost *:80>
        ServerAdmin webmaster@localhost
        ServerName ball.silverzhang.info
        ServerAlias ball.silverzhang.info

        ProxyRequests off
    <Proxy *>
        Order deny,allow
        Allow from all
    </Proxy>

    <Location />
        ProxyPass http://127.0.0.1:3000/
        ProxyPassReverse http://127.0.0.1:3000/
    </Location>
</VirtualHost>
{% endhighlight %}


