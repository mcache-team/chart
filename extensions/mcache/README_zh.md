# MCache

一个适用于各种不同架构的简单的缓存服务，由Golang开发，数据默认存储于内存中，当然支持用户自定义实现存储插件进行数据存储。

## 描述
MCache是一个内存缓存工具，一开始写这个工具主要是因为自己的一些项目经常需要在内存里缓存一些数据，并要实现类似于redis这种成型的缓存工具中都具备的一些多级查找、过期时间、类型等各种丰富的功能，但又不想引入一个外部的服务增加网络复杂性，因此就手写一个共用的模块，哪里需要就在哪里集成就行了。

在这基础上进行了功能扩展，让MCache能具备更多的能力，因此，我简单规划了下，后续会逐渐在里面实现几个方向的功能，当然，作为最基础的能力内置集成这块保证不受到影响。后续会增加HTTP、GRPC、QUICK、WS等多种协议，同时提供Watch机制，当然也有可能引入raft支持多节点同步的效果。

## 安装

默认的values配置足矣支持适用，如果你想要自定义，请自行定制`values.yaml`文件

## 测试

```shell
curl address/v1/data/test

# will get response cache not found
```

## 关于我

昵称：窝窝头(AlpheJangs)
邮箱: alphejangs@gmail.com
博客: https://alpherjang.github.io/
github主页:https://github.com/AlpherJang
个人简介: 关于MCache有任何建议意见，欢迎大家找交流