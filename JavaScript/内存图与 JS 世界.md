# 瓜分内存

![img](https://cdn.nlark.com/yuque/0/2021/png/21638555/1622188166966-ba417985-febd-4fc5-96ae-7e55e04bf2e8.png)

```javascript
let a = 1;
let b = 2;
```

a 和 b 这些变量会存上图中的不知道什么区(因为浏览器的分配规则是不一样的)

所有的数据都存到 **stack（栈）和 heap（堆）**

Stack 区特点：
- 存非对象数据和对象的地址
- 每个数据**顺序**存放

Heap 区特点：
- 存对象数据
- 每个数据**随机**存放
- 每个对象都会对应一个地址

只有数字、字符串、布尔这三个不是对象，其他的都是对象

```javascript
let a = 1
let b = a
let p = {...}
let p2 = p
```

= 号就是把右边的东西直接复制到左边（不存在什么传值和传址）

那如果让 `p2.name = 'xxx'`，那么 `p.name` 是多少呢？
- `p.name` 当然就是 `'xxx'` 了
- 因为 p2 和 p 都对应 #108 这个地址

![img](https://cdn.nlark.com/yuque/0/2021/png/21638555/1631286472830-862eb9dd-37fe-4930-8956-cae4c497fe70.png)