---
title: API Gateway 介绍
tags: [API,Kong,Nginx,Lua]
date: 2018-04-09
---

### 需求背景

公司发展壮大后，业务系统越来越多，每个系统都会提供不同的服务，这些服务一般包含内部服务(子系统之间数据调用)和外部服务(合作方之间数据调用)，目前各个服务大多是直接调用，随着服务数量增大，系统间的调用拓扑图就像一张蜘蛛网，难管理，并且每个服务都要实现自己的鉴权机制、流量控制等安全防护功能，导致冗余开发，由此我们需要在服务的上层建立一个网关，在网关层面做到 认证、限流、缓存、日志、监控报警等功能。

API网关使得搭建一个新的应用服务变得简单、快捷、高效，同时，将更多精力放在和业务紧密相关的工作上。

![](https://s0.dwz.st/blog/img/izl4hjzlkfetavmvcfe2m7n51ltkr7r4.jpg)
（传统接口调用）

![](https://s0.dwz.st/blog/img/0q4z3lb17fzobvx4omk2xfb10a3duvcz.jpg)

（API网关）

### API网关优点

* 易管理，提供API发布和管理功能，方便API检索查询。
* 鉴权/安全，将非法请求挡在服务之外。
* 限流，合理设置阈值，对后端服务起到保护作用。
* 日志，从日志中可以看出API调用量，状态码，响应时长，方便后续优化。
* 监控报警, 快速发现并且定位问题，解决故障。

### Kong 介绍

* [官网](https://konghq.com/)

Kong是Mashape公司开源的，基于Nginx_lua编写的API层软件。它主要作用是转发API通信和API网关管理,并且可以通过增加Kong Server进行水平扩展，通过前置负载均衡机器对Kong Server机器分发请求，达到负载均衡效果。

### Kong 优点

* Kong核心基于OpenResty构建，实现了请求/响应的Lua处理化。
* Kong可以运行在绝大部分操作系统上,易部署。
* Kong提供全套restful API，可以通过restful API构建我们自己的管理后台。
* Kong采用插件机制来定制Kong功能(Lua脚本语言编写)，并且官方已开发出大量插件，满足日常使用需求。

### Kong 官方插件截图

![](https://s0.dwz.st/blog/img/lhis6nxjhbtuvj3auzuirmcmjix59wp7.jpg)
认证、安全、限流、日志、分析监控等都已经包含。

### 参考链接

* [https://www.cnblogs.com/guozefeng/p/7468313.html](https://www.cnblogs.com/guozefeng/p/7468313.html)
* [https://getkong.org/docs/](https://getkong.org/docs/)

