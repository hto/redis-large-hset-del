# Large HSET keys delete
> If you afraid when large hash files has been deleted on Redis. You have to delete per single hash keys step by step.

> For example, you have a registered hash list of 30 million. If you delete it with the “del” command, you will probably have a huge load on your system. Or you may experience a crash.

> By scanning with the “HSCAN” command, I think it is the healthiest method to do this singular operation. 

## Usage
```shell
$ go build
```
### Run
> **Warning** cluster mode is DEFAULT. Or -clusterMode=false

> Deletes up to "-batchSize" every 3 seconds. Default 1000.

#### Examples
```shell
$ ./redis-large-hset-del -key=test
$ ./redis-large-hset-del -key=test -batchSize=2000
$ ./redis-large-hset-del -key=test -clusterMode=false
$ ./redis-large-hset-del -key=test -addr=127.0.0.1:6380
$ ./redis-large-hset-del -key=test -addr=127.0.0.1:6380 -password=123 
```

## Blog Links
- [Redis HSCAN command](https://redis.io/commands/hscan)
- [Lazy Redis is better Redis (Antirez)](http://www.antirez.com/news/93)
- [Deleting Large Hashes in Redis](https://redisgreen.net/blog/deleting-large-hashes/)


