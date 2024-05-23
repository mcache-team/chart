# MCache

MCache is a simple cache service suit for different architecture server, developed by Golang, as default cache data will save to memory, and support user custom define data plugin by them self.

## Description
MCache is a memory caching tool. Initially, I wrote this tool mainly because some of my projects often need to cache data in memory and implement various rich functions such as multi-level lookup, expiration time, and type that are commonly found in caching tools like Redis. However, I didn't want to introduce an external service to increase network complexity, so I wrote a shared module and integrated it wherever needed.

On this basis, functional extensions have been made to enable MCache to have more capabilities. Therefore, I have made a simple plan and will gradually implement functions in several directions in the future. Of course, as the most basic feature, the built-in integration is guaranteed not to be affected. In the future, multiple protocols such as HTTP, GRPC, QUICK, WS, etc. will be added, and a Watch mechanism will be provided. Of course, it is also possible to introduce the effect of raft supporting multi node synchronization.

## Install

Default values config is enough to run MCache, if you want to custom, please edit `values.yaml`.

## Test

```shell
# query data
curl http://127.0.0.1:8080/v1/data/test

# will get response cache not found

# write one record
curl --location --request PUT 'http://127.0.0.1:8080/v1/data' \
--header 'Content-Type: application/json' \
--data-raw '{
    "prefix":"test",
    "data":"test"
}'

# remove data
curl --location --request DELETE 'http://127.0.0.1:8080/v1/data/test'
```
more usage demo and features please visit homepage(https://mcache-team.github.io/mcache/) of MCache to learning.

## About Me

- Nickname：窝窝头(AlpheJangs)
- Email: alphejangs@gmail.com
- Blog: https://alpherjang.github.io/
- Github Page:https://github.com/AlpherJang
- Person Introduce: years of experience in cloud native development, enjoy building my own wheels
- Any suggestion about MCache, please connect me.