# MCache

一个适用于各种不同架构的简单的缓存服务，由Golang开发，数据默认存储于内存中，当然支持用户自定义实现存储插件进行数据存储。

## 描述
MCache是一个内存缓存工具，一开始写这个工具主要是因为自己的一些项目经常需要在内存里缓存一些数据，并要实现类似于redis这种成型的缓存工具中都具备的一些多级查找、过期时间、类型等各种丰富的功能，但又不想引入一个外部的服务增加网络复杂性，因此就手写一个共用的模块，哪里需要就在哪里集成就行了。

在这基础上进行了功能扩展，让MCache能具备更多的能力，因此，我简单规划了下，后续会逐渐在里面实现几个方向的功能，当然，作为最基础的能力内置集成这块保证不受到影响。后续会增加HTTP、GRPC、QUICK、WS等多种协议，同时提供Watch机制，当然也有可能引入raft支持多节点同步的效果。

## 安装

默认的values配置足矣支持适用，如果你想要自定义，请自行定制`values.yaml`文件

## 测试

```shell
# 查询数据
curl http://127.0.0.1:8080/v1/data/test

# will get response cache not found

# 写入一条数据
curl --location --request PUT 'http://127.0.0.1:8080/v1/data' \
--header 'Content-Type: application/json' \
--data-raw '{
    "prefix":"test",
    "data":"test"
}'

# 删除数据
curl --location --request DELETE 'http://127.0.0.1:8080/v1/data/test'
```

更多的使用方式以及特性请访问MCache的项目主页进行学习了解: https://mcache-team.github.io/mcache/

## 关于我

- 昵称：窝窝头(AlpheJangs)
- 邮箱: alphejangs@gmail.com
- 博客: https://alpherjang.github.io/
- github主页:https://github.com/AlpherJang
- 个人简介: 多年的云原生开发经验，喜欢自己造轮子 
- 关于MCache有任何建议意见，欢迎大家找我交流