# Redis

一个基于内存的单线程高性能key-value型数据库，读写性能优异。



## 下载安装

下载地址：https://github.com/microsoftarchive/redis/releases

打开下载链接：打开Assets，选择对应格式下载

安装或解压后目录

打开服务：redis-server.exe

连接客户端：redis-cli.exe



## 支持丰富数据类型

1. string：字符串
2. list：链表
3. set：集合
4. zset：sorted set 有序集合
5. hash：哈希类型



## 操作



> 清空数据库
>
> flushdb



### 字符串

```
set name 'kyle'
get name

set sex 'man'
get sex

del name
del sex

exists name
exists sex
```



### List集合

```
//lpush 在列表左侧开始添加 执行完后 顺序是 '3' '2' '1'
lpush my_list '1' '2' '3'

//全部列出来
lrange my_list 0 -1

//rpush 在列表右侧添加 执行完后 顺序 '3' '2' '1' 'love'
rpush my_list 'love'

//更新指定位置的值
lset my_list 0 'index'

lrem my_list 0
//删除指定位置(后面的值是校验的作用)
lrem my_list 0 'index'

```



### Set集合

```
sadd my_set 'ay' 'by' 'cy'

smembers my_set

srem m_set 'ay'

```





### Hash集合

```
//创建my_hset，设置 名'name' 值 'kyle'
hset my_hset 'name' 'kyle'

hset my_hset 'sex' 'man'

hset my_hset 'name' 'matt'

hget my_hset 'name'

hgetall my_hset

hdel my_hset 'name'

//查询长度
hlen my_hset

hkeys my_hset

hvals my_hset

```





### SortedSet 集合（有序）

```
// 分数1
zadd my_zset 1 'ay'

// 分数2
zadd my_zset 2 'by'

// 分数3
zadd my_zset 3 'cy'


zrange my_zset 0 -1
>> 'ay' 'by' 'cy'

zrevrange my_zset 0 -1
>> 'cy' 'by' 'ay'

zscore my_zset 'ay'
>> 1


```



### 引入依赖

在 `pom.xml` 文件中引入依赖

```xml
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-data-redis</artifactId>
        </dependency>
```



### 添加配置

在`application.properties` 文档中添加 `Redis`配置

```properties
### Redis 配置
### 默认redis数据库为db0
spring.redis.database=0
### 服务器地址，默认localhost
spring.redis.host=localhost
### 链接端口，默认63769
spring.redis.port=6379
### redis密码默认为空
spring.redis.password=
```

