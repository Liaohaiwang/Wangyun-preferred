**1 项目介绍**

社区团购是真实居住社区内居民团体的一种互联网线上线下购物消费行为，是依托真实社区的一种区域化、小众化、
本地化、网络化的团购形式。简而言之，它是依托社区和团长社交关系实现生鲜商品流通的新零售模式。
比如：
美团优选，是美团旗下的一个社区团购平台，通过自建和加盟的方式，在全国建立了大仓、网格仓、线下服务门店的
物流配送体系。美团优选卖的东西也特别的全，蔬菜、水果、肉类、蛋类，然后海鲜等等。
![SJZ4N_BDX5$J3A4KXM@VH9I](https://github.com/Liaohaiwang/Wangyun-preferred/assets/86451316/42d1cd35-33cc-43e3-868d-89ba56c75feb)

多多买菜，它是拼多多旗下的产品，拼多多现在已经是全中国最大的生鲜电商了，它和全国超过一千个农产品产区达
成合作。
![}(`_7{`ZQ FD_X0O98R8~KK](https://github.com/Liaohaiwang/Wangyun-preferred/assets/86451316/344caf50-c515-420e-b5b8-e2418888c149)

**2 业务流程**

从具体模式看，主要围绕平台、团长、用户三个角色展开：
1、团长（如社区宝妈、便利店老板等）创建一个群，提前发布优惠商品的链接供用户购买，团长从中抽取佣金；
2、用户提前一天下单；
3、平台在收集好订单之后，调动供应链，从仓库发货到自提点（团长家或者便利店）；
4、用户前往自提点提货
![1_8}D @W6UFE %4M}WK }J4](https://github.com/Liaohaiwang/Wangyun-preferred/assets/86451316/ac37e0ef-ba79-4314-81b7-78e8db746336)

**3 功能架构**

功能架构分为三层
1、前台会员应用层
2、前台团长应用层
3、基础模块支撑层
![T7)FO_LK165``%GBH4U~BXA](https://github.com/Liaohaiwang/Wangyun-preferred/assets/86451316/f95849f8-bf5f-4d9c-9418-e4d26e66e66a)

**4 技术架构**

![N3O{ ~KGFIJDOU(C0ZPWU P](https://github.com/Liaohaiwang/Wangyun-preferred/assets/86451316/fb3458fe-adbb-4ffe-a1c4-0cfd1d60bd02)

**5 核心技术**
SpringBoot：简化新Spring应用的初始搭建以及开发过程
SpringCloud：基于Spring Boot实现的云原生应用开发工具，SpringCloud使用的技术：（Spring Cloud Gateway、
Spring Cloud OpenFeign、Spring Cloud Alibaba Nacos等）
MyBatis-Plus：持久层框架
Redis：缓存数据库
Redisson：基于redis的Java驻内存数据网格，实现分布式锁
RabbitMQ：消息中间件
ElasticSearch +Kibana: 全文检索服务器 +可视化数据监控
ThreadPoolExecutor：线程池来实现异步操作，提高效率
OSS：文件存储服务
Knife4j（Swagger）：Api接口文档工具
Nginx：负载均衡
MySQL：关系型数据库
微信支付
微信小程序
Docker：容器技术
DockerFile：管理Docker镜像命令文本

**6 项目模块**

![A0%TP@JQ4U%1BE}RC6%IT3Q](https://github.com/Liaohaiwang/Wangyun-preferred/assets/86451316/bb431dbe-aab6-4d6d-a14e-2033141a3e5e)

最终服务器端架构模块
huaihua-hhyx-parent：父工程，根目录，管理子模块：
common：公共类父模块
common-util：核心工具类
service-util：service模块工具类
rabbit-util：RabbitMQ工具类
model：实体类模块
service：系统微服务模块
**service-client：系统远程调用封装模块

7 其他资源**
实体类、数据库脚本、项目中使用的工具类、前端源码等都在资料文件夹中，实体类直接复制到model模块，后续不
做说明。

**二 前后端分离开发概述**

**1 什么是前后端分离开发**
前后端分离开发，就是在项目开发过程中，对于前端的代码专门由前端的开发人员开发，后端代码由后端人员负责，
这样可以做到分工明确、各司其职，进而提高开发效率，前后端代码并行开发，加快项目的开发进度。目前前后端分
离被各大公司使用，成为项目开发的主流开发方式。前后端分离开发后，工程结构也会发生变化，即前后端代码不会
混在同一个maven工程中，而是分为前端工程和后端工程。
在美国等互联网环境比较发达的国家项目开发的分工协作更为明确，整个项目开发分为前端、中间层和后端三个开发
阶段，这三个阶段分别由三个或者更多的人来协同完成。国内的大部分互联网公司只有前端工程师和后端工程师，中
间层的工作有的由前端来完成，有的由后端来完成。

**2 开发流程介绍**

![AN)769JW(FW)X OZ)1%~QGK](https://github.com/Liaohaiwang/Wangyun-preferred/assets/86451316/b26db8e2-998e-40d1-bae1-7314c5b8b88a)

前后端分离开发过程中，前端人员和后端人员要进行配合来共同完成一个任务。这个时候需要使用到接口。 接口
（API接口）：是一个http的请求地址，主要是定义：请求路径、请求方式、请求参数、响应数据等内容。 （1）后
端编写和维护接口文档，在 API 变化时更新接口文档 （2）后端根据接口文档进行接口开发 （3）前端根据接口文档
进行开发 （4）开发完成后联调和提交测试
后端开发人员为前端提供接口的同时，还需同时提供接口的说明文档。但我们的代码总是会根据实际情况来实时更
新，这个时候有可能会忘记更新接口的说明文档，造成一些不必要的问题。我们可以通过一些工具生成接口文档，做
到文档实时更新。Swagger 是一个规范和完整的框架，用于生成、描述、调用和可视化 RESTful 风格的 Web 服务的
接口文档。
