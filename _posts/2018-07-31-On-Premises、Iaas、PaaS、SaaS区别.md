---
layout: post
title: "On-Premises、Iaas、PaaS、SaaS区别"
categories: cloud
description: "On-Premises、Iaas、PaaS、SaaS区别"
keywords: cloud
date: 2018-07-31 11:45:00
---

如何理解云计算，就像吃货想吃披萨了...

是时候祭出这篇吃货文章了：

![image](/images/blog/cloud/image001.jpeg)

你一定听说过云计算中的三个“高大上”的你一定听说过云计算中的三个“高大上”的概念：IaaS、PaaS和SaaS，这几个术语并不好理解。**不过，如果你是个吃货，还喜欢披萨，这个问题就好解决了!**好吧，其实你根本不是一个吃货，之所以自我标榜为吃货，其实是为了收获赞叹式的夸奖，“吃货还这么瘦，好羡慕啊!”或者，总得给伦家的微丰找个像样的理由。

## 一个“吃货”是怎样吃到披萨的呢?

1. 在家自己做
这真是个麻烦事，你的准备很多东西，发面、做面团、进烤箱。。。。。简单列一下，需要下图所示的一切：

![image](/images/blog/cloud/image002.jpeg)

2. 买好速食披萨回家自己做着吃
你只需要从披萨店里买回成品，回家烘焙就好了，在自己的餐桌上吃。和自己在家做不同，你需要一个pizza供应商。

![image](/images/blog/cloud/image003.jpeg)

3. 打电话叫外卖将披萨送到家中
打个电话，pizza就送到家门口。

![image](/images/blog/cloud/image004.jpeg)

4.在披萨店吃披萨
你什么都不需要准备，连餐桌也是pizza店的。

![image](/images/blog/cloud/image005.jpeg)

总结一下，吃货可以通过如下途径吃披萨：

![image](/images/blog/cloud/image006.jpeg)

## 好了，现在忘掉pizza!

假设你是一家超牛X的技术公司，根本不需要别人提供服务，你拥有基础设施、应用等等其它一切，你把它们分为三层：**基础设施(infrastructure)**、**平台(platform)**和**软件(software)**，如下图：

![image](/images/blog/cloud/image007.jpeg)

这其实就是云计算的三个分层，基础设施在最下端，平台在中间，软件在顶端，分别是分别是Infrastructure-as-a-Service(IaaS)，Platform-as-a-Service(PaaS)，Software-as-a-Service(SaaS)，别的一些“软”的层可以在这些层上面添加。

而你的公司什么都有，现在所处的状态叫本地部署(On-Premises)，就像在自己家做pizza一样。几年前如果你想在办公室或者公司的网站上运行一些企业应用，你需要去买服务器，或者别的高昂的硬件来控制本地应用，让你的业务运行起来，这就叫本地部署。

假如你家BOSS突然有一天想明白了，只是为了吃上pizza，为什么非要自己做呢?于是，准备考虑一家云服务供应商，这个云服务供应商能提供哪些服务呢?其所能提供的云服务也就是云计算的三个分层：IaaS、PaaS和SaaS，就像pizza店提供三种服务：买成品回家做、外卖和到披萨店吃。

用一张图来表示就是这样的。

![image](/images/blog/cloud/image008.jpeg)

## 现在我们来谈谈具体细节。

### IaaS: Infrastructure-as-a-Service(基础设施即服务)
有了IaaS，你可以将硬件外包到别的地方去。IaaS公司会提供场外服务器，存储和网络硬件，你可以租用。节省了维护成本和办公场地，公司可以在任何时候利用这些硬件来运行其应用。

一些大的IaaS公司包括Amazon, Microsoft, VMWare, Rackspace和Red Hat.不过这些公司又都有自己的专长，比如Amazon和微软给你提供的不只是IaaS，他们还会将其计算能力出租给你来host你的网站。

### PaaS: Platform-as-a-Service(平台即服务)
第二层就是所谓的PaaS，某些时候也叫做中间件。你公司所有的开发都可以在这一层进行，节省了时间和资源。

PaaS公司在网上提供各种开发和分发应用的解决方案，比如虚拟服务器和操作系统。这节省了你在硬件上的费用，也让分散的工作室之间的合作变得更加容易。网页应用管理，应用设计，应用虚拟主机，存储，安全以及应用开发协作工具等。
一些大的PaaS提供者有Google App Engine,Microsoft Azure，Force.com,Heroku，Engine Yard。最近兴起的公司有AppFog,Mendix和Standing Cloud.

### SaaS: Software-as-a-Service(软件即服务)
第三层也就是所谓SaaS。这一层是和你的生活每天接触的一层，大多是通过网页浏览器来接入。任何一个远程服务器上的应用都可以通过网络来运行，就是SaaS了。
你消费的服务完全是从网页如Netflix,MOG,Google Apps,Box.net,Dropbox或者苹果的iCloud那里进入这些分类。尽管这些网页服务是用作商务和娱乐或者两者都有，但这也算是云技术的一部分。

一些用作商务的SaaS应用包括Citrix的Go To Meeting，Cisco的WebEx，Salesforce的CRM，ADP，Workday和SuccessFactors。