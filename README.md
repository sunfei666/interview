# interview

## 算法与数据结构


#### [拜托，面试别再问我TopK了！！！](https://mp.weixin.qq.com/s/FFsvWXiaZK96PtUg-mmtEw)
#### [小米三面面试题](https://github.com/TomorrowWu/golang-algorithms/blob/master/algorithms/uncategorized/%E5%B0%8F%E7%B1%B3%E4%B8%89%E9%9D%A2%E9%9D%A2%E8%AF%95%E9%A2%98/README.md)

### 数组
#### [实现Array](https://github.com/TomorrowWu/golang-algorithms/blob/master/data-structures/array/array.go)

### 链表
#### [实现linked-list及相关操作,链表反转,判断循环链表,合并两个有序链表,删除倒数第n个节点](https://github.com/TomorrowWu/golang-algorithms/blob/master/data-structures/linked-list/singlelinkedlist.go)
#### [单向链表判断是否回文](https://github.com/TomorrowWu/golang-algorithms/blob/master/data-structures/linked-list/palindrome.go)

### 栈
#### [为什么函数调用要用“栈”来保存临时变量]()
#### [JVM中的"栈"和数据结构中的"栈"是一回事吗?](算法与数据结构/栈/JVM中的"栈"和数据结构中的"栈"是一回事吗?.md)
#### [栈在表达式求值中应用(带小括号)]()
#### [基于数组实现栈数据结构]()
#### [基于单链表实现栈数据结构]()
#### [基于栈结构实现浏览器前进和后退功能]()

### 队列
#### [哪些场景中会用到队列的排队请求?](算法与数据结构/队列/哪些场景中会用到队列的排队请求?.md)
#### [实现无锁并发队列]()

### 跳表
#### [为什么Redis要用跳表来实现有序集合，而不是红黑树](算法与数据结构/跳表/为什么Redis要用跳表来实现有序集合，而不是红黑树.md)

### 递归
#### [对递归的理解](算法与数据结构/递归/对递归的理解.md)

### 排序
#### [特定算法是依赖特定的数据结构的,排序算法一般都是基于数组实现的,如果数据存储在链表中,排序算法还能工作吗?如果能,那相应的时间复杂度、空间复杂度又是多少呢?](算法与数据结构/排序/基于链表存储,排序算法思考?.md)
#### [10个接口访问日志文件,每个文件约300MB,每个文件的日志都是按照时间戳从小到大排序的,将10个文件合并为1个文件,仍按照时间戳从小到大排列,如果处理任务的机器内存只有1GB,有什么好的解决思路,能"快速"地将这10个文件合并?]()
```
先构建十条io流，分别指向十个文件，每条io流读取对应文件的第一条数据，
然后比较时间戳，选择出时间戳最小的那条数据，将其写入一个新的文件，
然后指向该时间戳的io流读取下一行数据，然后继续刚才的操作，比较选出最小的时间戳数据，写入新文件，io流读取下一行数据，
以此类推，完成文件的合并， 
这种处理方式，日志文件有n个,数据就要比较n次，每次比较选出一条数据来写入，时间复杂度是O（n），空间复杂度是O（1）,几乎不占用内存，
```
#### [在O(n)内查找第K大元素,代码实现](https://github.com/TomorrowWu/golang-algorithms/blob/master/leetcode/0215.kth-largest-element-in-an-array/src/kth-largest-element-in-an-array.go)
#### 根据年龄,给100万用户排序
计数排序
#### [拜托，面试别再问我计数排序了！！！](https://mp.weixin.qq.com/s/KU-AUGOnLeRtE_hivl2uSA)
#### [拜托，面试别再问我基数排序了！！！](https://mp.weixin.qq.com/s/Z8gU9QLpMnA-zoMc9ZeR2w)
#### 如何在1000万个整数中快速查找某个整数?(内存限制是100MB,每个数据大小是8字节)
```
- 解决: 将数据存储在数组中,内存占用80MB,从小到大排序,再二分查找算法
- 散列表和二叉树等支持快速查找的动态数据结构,大部分情况下,二分查找可以解决的问题,用上述两种数据结构都可以解决
- 但是,上述两种结构需要比较多的额外的内存空间,100MB内存存不下
- 二分查找底层依赖的是数组,除了数据本身以外,不需要额外存储其他信息,最省内存
```

### 二分查找
#### [如何快速定位IP对应的省份地址？](算法与数据结构/二分查找/如何快速定位IP对应的省份地址.md)

### 散列表（Hash表）
#### [如何设计一个工业级的散列表](算法与数据结构/散列表/如何设计一个工业级的散列表.md)

### 树
#### [说说树的概念](算法与数据结构/树/树的概念.md)
#### [给定一组数据，比如 1，3，5，6，9，10，可以构建出多少种不同的二叉树？]()
#### [如何实现按层遍历二叉树？]()
#### [散列表如此高效，为什么还需要二叉树？](算法与数据结构/树/散列表、二叉查找树对比.md)
#### 如何通过编程，求给定一棵二叉树的确切高度
```
- 第一种是深度优先思想的递归，分别求左右子树的高度。当前节点的高度就是左右子树中较大的那个+1
- 第二种可以采用层次遍历的方式，每一层记录都记录下当前队列的长度，这个是队尾，每一层队头从0开始。
然后每遍历一个元素，队头下标+1。直到队头下标等于队尾下标。这个时候表示当前层遍历完成。
每一层刚开始遍历的时候，树的高度+1。最后队列为空，就能得到树的高度。
```

### 哈希算法
#### [哈希算法有哪些应用场景](算法与数据结构/哈希算法/哈希算法的应用场景.md)

##   计算机网络
#### [如果一个局域网里面有多个交换机,ARP广播的模式会出现什么问题呢?](网络协议/一个局域网里面有多个交换机,会出现什么问题.md)
#### [ARP协议,已知IP地址求MAC;RARP协议,已知MAC求IP,可以用来做什么?](网络协议/RARP协议的作用.md)
#### [STP协议能够很好的解决环路问题,但是也有它的缺点,你能举几个例子吗?](网络协议/STP协议的缺点.md)
#### [在一个比较大的网络中,如果两台机器不通,你知道应该用什么方式调试吗?](网络协议/两台机器不通,如何调试?.md)
#### [你觉得基于RTMP的视频流传输的机制存在什么问题？如何进行优化？](网络协议/揭秘RTMP流媒体协议.md)
#### [把电影下载下来看，那么大，如何快速下载？](网络协议/快速下载.md)
#### 负载均衡为什么要分地址和运营商呢？
```
为了返回最优的IP，即离用户最近的IP，提高访问速度
```

## MySQL


## 网络协议
#### [TCP和UDP的区别](网络协议/TCP和UDP的区别.md)
#### [UDP的特点及使用场景](网络协议/UDP的特点及使用场景.md)
#### [用websocket连接服务器时，为什么要自己做心跳机制，tcp不是有心跳机制？](网络协议/TCP和UDP的区别.md)


## 分布式系统
#### [PoW和Paxos/Raft对比](分布式系统/PoW,Paxos,Raft对比.md)

## 区块链
#### [比特币中PoW的优劣](区块链/比特币中PoW的优劣.md)

## 系统设计
#### [基于Redis做IP限速](https://redis.io/commands/incr)
