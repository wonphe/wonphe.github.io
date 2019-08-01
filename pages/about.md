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

## 打赏

![支付宝红包]({{ website.url }}/YueDu/zfbhbrwm.jpg)

![支付宝收款码]({{ website.url }}/YueDu/zfbhbrwm.jpg)

![微信收款码]({{ website.url }}/YueDu/zfbhbrwm.jpg)

![QQ收款码]({{ website.url }}/YueDu/zfbhbrwm.jpg)

## Skill Keywords

{% for category in site.data.skills %}
### {{ category.name }}
<div class="btn-inline">
{% for keyword in category.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
