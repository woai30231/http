# 《HTTP权威指南》概念手册

## *前言*

* 需要说明一下，因为一直有在看《HTTP权威指南》，觉得这是一本很值得称赞的一本高质量的书籍，书中内容涵盖很全面，而且配以插图，使得阅读起来很容易理解！无论是对于已经踏足开发领域的老手，还是刚接触相关领域的新手，都可以接触。所以很推荐大家从头到尾过一遍，我相信看过之后对某些概念将会有一个更深层次的理解！当然了，我的建议是对这本书多过几遍，因为这样才能加深映像同时加深理解！毕竟常言道：“书读百遍，其意自见、温故而知新等都说明了书需要多次阅读才能体会其意，才能从中读出更深层次的含义”！

* 首先说明一下，这个文档并不是要超越《HTTP权威指南》原书，文档中描述到的所有概念都是基于原书的！因为原书对相关概念介绍的太过仔细，所以原书的篇幅过于太长，而我常常出现的情况是对原书中的一些概念记忆模糊，需要通过再次查看才能回忆起来，可是我发现每次重新去找某些知识点的时候，发现是一个很耗时、复杂的过程，因为得到相关章节一页一页的去找，而我只是对于某个概念“模糊”而已，所以我觉得这个过程是不必要的，同时，我希望通过自己在文档中对原书的一些概念进行提炼性的总结来加深自己的记忆映像！因此才有了这个文档的诞生！

* 切记！！此文档是基于原书的，所以希望读者都是看过原书的。所以你没有看过原书，而直接来这里看，那么是没有意义的，因为本文档没有图文并茂的实例，更没有代码供查看，有的只是从原书中copy过来的“提炼过”的文字、概念而已。

* 最最最后再说一下，由于本人的文字总结能力也有很多不足，所以有些地方表达不是很到位的地方，那么请您以原书为主！再次感谢的阅读！




## 目录

### *[第一章 HTTP概述](https://github.com/woai30231/http/tree/master/%E7%AC%AC%E4%B8%80%E7%AB%A0%20HTTP%20%E6%A6%82%E8%BF%B0)*


### *[第二章 URL与资源](https://github.com/woai30231/http/tree/master/%E7%AC%AC%E4%BA%8C%E7%AB%A0%20URL%E4%B8%8E%E8%B5%84%E6%BA%90)*


### *[第三章 HTTP报文](https://github.com/woai30231/http/tree/master/%E7%AC%AC%E4%B8%89%E7%AB%A0%20HTTP%E6%8A%A5%E6%96%87)*


### *[第四章 连接管理](https://github.com/woai30231/http/tree/master/%E7%AC%AC%E5%9B%9B%E7%AB%A0%20%E8%BF%9E%E6%8E%A5%E7%AE%A1%E7%90%86)*

### *[第五章 web服务器](https://github.com/woai30231/http/tree/master/%E7%AC%AC%E4%BA%94%E7%AB%A0%20web%E6%9C%8D%E5%8A%A1%E5%99%A8)*

### *[第六章 代理](https://github.com/woai30231/http/tree/master/%E7%AC%AC%E5%85%AD%E7%AB%A0%20%E4%BB%A3%E7%90%86)*

### *[第七章 缓存](https://github.com/woai30231/http/tree/master/%E7%AC%AC%E4%B8%83%E7%AB%A0%20%E7%BC%93%E5%AD%98)*

### *[第八章 集成点：网关、隧道及中继](https://github.com/woai30231/http/tree/master/%E7%AC%AC%E5%85%AB%E7%AB%A0%20%E9%9B%86%E6%88%90%E7%82%B9%EF%BC%9A%E7%BD%91%E5%85%B3%E3%80%81%E9%9A%A7%E9%81%93%E5%8F%8A%E4%B8%AD%E7%BB%A7)*

### *[第九章 Web机器人](https://github.com/woai30231/http/tree/master/%E7%AC%AC%E4%B9%9D%E7%AB%A0%20Web%E6%9C%BA%E5%99%A8%E4%BA%BA)*

### *[第十章 HTTP-NG](https://github.com/woai30231/http/tree/master/%E7%AC%AC%E5%8D%81%E7%AB%A0%20HTTP-NG)*

### *[第十一章 客户端识别与Cookie机制](https://github.com/woai30231/http/tree/master/%E7%AC%AC%E5%8D%81%E4%B8%80%E7%AB%A0%20%E5%AE%A2%E6%88%B7%E7%AB%AF%E8%AF%86%E5%88%AB%E4%B8%8ECookie%E6%9C%BA%E5%88%B6)*

### *[第十二章 基本认证机制](https://github.com/woai30231/http/tree/master/%E7%AC%AC%E5%8D%81%E4%BA%8C%E7%AB%A0%20%E5%9F%BA%E6%9C%AC%E8%AE%A4%E8%AF%81%E6%9C%BA%E5%88%B6)*

### *[第十三章 摘要认证](https://github.com/woai30231/http/tree/master/%E7%AC%AC%E5%8D%81%E4%B8%89%E7%AB%A0%20%E6%91%98%E8%A6%81%E8%AE%A4%E8%AF%81)*

### *[第十四章 安全HTTP](https://github.com/woai30231/http/tree/master/%E7%AC%AC%E5%8D%81%E5%9B%9B%E7%AB%A0%20%E5%AE%89%E5%85%A8HTTP)*

### *[第十五章 实体和编码](https://github.com/woai30231/http/tree/master/%E7%AC%AC%E5%8D%81%E4%BA%94%E7%AB%A0%20%E5%AE%9E%E4%BD%93%E5%92%8C%E7%BC%96%E7%A0%81)*