---
layout:     post
title:      "Welcome to my Blog"
subtitle:   " \"Hello World, Hello Blog\""
date:       2016-03-22 22:34:00
author:     "dcmi"
header-img: "img/post-bg-2016.jpg"
tags:
    - 生活
---

> “Yeah It's on. ”


## 前言

ChaoSir 的 Blog 就这么开通了。

[跳过废话，直接看技术实现 ](#build)



2016年，在我看了许多前端相关的书籍和技术博客后，我想做一个自己的博客，github pages这个免费的静态站点吸引了我。


作为一个程序员， Blog 这种轮子要是挂在大众博客程序上就太没意思了。一是觉得大部分 Blog 服务都太丑，二是觉得不能随便定制不好玩。之前因为太懒没有折腾，结果就一直连个写 Blog 的地儿都没有。


<p id = "build"></p>
---

## 正文

接下来说说搭建这个博客的技术细节。  

正好之前就有关注过 [GitHub Pages](https://pages.github.com/) + [Jekyll](http://jekyllrb.com/) 快速 Building Blog 的技术方案，非常轻松时尚。

其优点非常明显：

* **Markdown** 带来的优雅写作体验
* 非常熟悉的 Git workflow ，**Git Commit 即 Blog Post**
* 利用 GitHub Pages 的域名和免费无限空间，不用自己折腾主机
	* 如果需要自定义域名，也只需要简单改改 DNS 加个 CNAME 就好了
* Jekyll 的自定制非常容易，基本就是个模版引擎


本来觉得最大的缺点可能是 GitHub 在国内访问起来太慢，所以第二天一起床就到 GitCafe(Chinese GitHub Copy) 迁移了一个[镜像](http://huxpro.gitcafe.io)出来，结果还是巨慢。

果断开 Chrome DevTool 查了下网络请求，原来是 **pending 在了 Google Fonts** 上，页面渲染一直被阻塞到请求超时为止，难怪这么慢。  
忍痛割爱，只好把 Web Fonts 去了（反正超时看到的也只能是 fallback ），果然一下就正常了，而且 GitHub 和 GitCafe 对比并没有感受到明显的速度差异，虽然 github 的 ping 值明显要高一些，达到了 300ms，于是用 DNSPOD 优化了一下速度。



---

配置的过程如下：
 1.[安装jekyll：](http://jekyllrb.com/)

 $ gem install jekyll
 
 但是在安装rubyGems的时候遇到了error，百度一查，原来大家都和我一样嘛，国内的网被屏蔽了o(︶︿︶)o ，所以我们借用jekyll官方文档说的方法：安装之前需要配置ruby和rubyGems的环境,安装 Jekyll 的最好方式就是使用 RubyGems。
 ，于是看到别的解决方法————淘宝团队搭建的ruby gems镜像：
   $ gem sources --remove https://rubygems.org/
   $ gem sources -a https://ruby.taobao.org/
   $ gem sources -l
	  *** CURRENT SOURCES ***
	  https://ruby.taobao.org
 2.这时候安装好了rubyGems，就可以很愉快的安装jekyll了，重复第一步的步骤。





