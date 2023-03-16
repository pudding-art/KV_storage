# KV_storage
存储方向项目学习，主要包括内存版KV（以Redis为例）以及文件版KV（以LevelDB实现为例）进行学习。

实现目标：实现Key-Value数据库，两个方向：内存KV数据库（Redis）；文件版本KV数据库（Leveldb）
KV存储实现设计核心：
	1. 在大前提下保证数据安全和尽可能提高读写性能

内存版KV
数据结构：hash table， 跳表（比其他数据结构更容易做并发）
高性能读和写
数据
进程被kill，或者宕机怎么恢复数据（预写式日志WAL，日志设计）
进一步：服务端-客户端架构实现
参考：Redis实现

文件版KV
数据结构：LSMTree, 布隆过滤器（有一定误差的情况下检查key的存在性）
Key特别多的情况下，还能高性能读和取
数据持久化、文件格式设计
进程被kill，或者宕机怎么恢复数据（预写式日志WAL，日志设计）
参考：LevelDB实现

学习资料（更新中）
https://leveldb-handbook.readthedocs.io/zh/latest/
leveldb实现解析 - 淘宝-核心系统研发-存储
Wisckey实现
leveldb源码![image](https://user-images.githubusercontent.com/60512507/225498236-0f2457e0-c6c5-45ba-ac97-3b921adaa98b.png)

