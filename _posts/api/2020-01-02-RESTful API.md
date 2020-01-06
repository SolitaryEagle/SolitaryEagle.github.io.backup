---
layout: post
title: RESTful API
category: API
tags: API
---
> [设计你的第一个 REST API：第一部分](https://www.infoq.cn/article/0x6ti40gBjhcHJc2JVT7)
>
> [REST 介绍](https://dzone.com/refcardz/rest-foundations-restful?chapter=1)
>
> [深入浅出 REST](https://www.infoq.cn/article/rest-introduction/)

# 误解
1. REST 是通过 url 来调用 web 服务.

# 关键点

REST 最好用于管理系统, 方法是将生产和消费的信息与生产和消费它的技术分离开.

应该以适合客户端使用模式的方式来设计资源, 而不是基于现有的数据库或对象模式. (这不是违背了服务端以一种方式响应不同客户端的初衷了吗?)

# 特性
* 性能(Performance)
* 性能可扩展性(Scalability)
* 概括性(Generality)
* 简单性(Simplicity)
* 可修改性(Modifiability)
* 功能可扩展性(Extensibility)

# 理查森成熟度模型
SOAP(简易对象访问协议)与REST(表示状态转移)的区别

| 等级 | 区别 |
| ------ |-------------------
|  0   |这基本上就是 SOAP 所在的地方.没有信息资源, HTTP 被当作传输协议, 也没有超媒体的概念. 结论: REST 和 SOAP 是不同的方法
|  1   |使用了 url, 但并不总是作为适当的信息资源, 所有的东西通常都是 GET 请求(包括更新服务器状态的请求). 大多数刚接触 REST 的人首先构建这样的系统
|  2   |url 用于表示信息资源, HTTP 被视为一种应用程序协议, 有时还包括内容协商. 大多数面向 Internet 的 “REST”web 服务实际上只在这个级别, 因为它们只支持非超媒体格式
|  3   |url 用于表示信息资源, HTTP 作为包括内容协商的应用程序协议而受到重视. 超媒体驱动客户机的交互

# 动词

|  动词   | 操作              | 成功响应码 |     幂等性     |返回值          |
| ------  | ---------------- | --------- | ------------- |---------------|
| GET     | 查询操作          | 200       | 幂等           | 返回资源 JSON  |
| POST    | 新增资源          | 201       | 不安全也不幂等  | 返回资源标识符  |
| PUT     | 全量更新资源      | 200       | 幂等           | 返回 void      |
| DELETE  | 删除资源          | 200       | 幂等          | 返回 void     |
| HEAD    | 检索资源是否存在   | 200       | 幂等          | 返回 void     |
| OPTIONS | 询问资源支持的动词 | 200       | 幂等          | 返回支持的动词  |

# 总结
* 首先确定资源 ==> 确定资源路径URI(与资源一一对应)  ==>  确定动词
* 入参与与出参应该尽量可视化, 不必过于拘泥于OOP; 如 id 应该明确为 bookId 还是 imageId




