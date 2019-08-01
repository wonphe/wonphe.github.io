---
layout: page
title: About
description:
keywords: '0x16'
comments: true
menu: 关于
permalink: /about/
---

## 联系

{% for website in site.data.social %}
* {{ website.sitename }}：[@{{ website.name }}]({{ website.url }})
{% endfor %}

## Skill Keywords

{% for category in site.data.skills %}
### {{ category.name }}
<div class="btn-inline">
{% for keyword in category.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}

## 打赏

[![支付宝红包]({{ website.url }}/YueDu/zfbhbrwm.jpg){:height="300" width="200"}]({{ website.url }}/YueDu/zfbhbrwm.jpg)

[![支付宝收款码]({{ website.url }}/YueDu/zfbskrwm.jpg){:height="300" width="200"}]({{ website.url }}/YueDu/zfbskrwm.jpg)

[![微信收款码]({{ website.url }}/YueDu/wxskrwm.png){:height="300" width="200"}]({{ website.url }}/YueDu/wxskrwm.png)

[![QQ收款码]({{ website.url }}/YueDu/qqskrwm.png){:height="300" width="200"}]({{ website.url }}/YueDu/qqskrwm.png)
