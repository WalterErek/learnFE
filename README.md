# learnFE
some essays on the way to be a FEer

## 在路上，永远热泪盈眶
## 陪着小豆芽一起成长

---

## 20200926
+ [【前端体系】从一道面试题谈谈对EventLoop的理解](https://juejin.im/post/6868849475008331783#heading-18)
+ 再温习了一遍eventloop
+ tips:
```
.then需要等状态确定后才能知道注册then还是catch，因此状态还没有确定之前下面的then中的回调都不会注册当异步任务中
finally无论状态有没有变都能够触发，因此会不依赖于状态改变注册
```

## 20200927
+ toFixed采用的银行家算法
例如：(76.845).toFixed(2) // '76.84'
银行家算法
四舍六入五考虑，五后非空就进一，五后为空看奇偶，五前为偶应舍去，五前为奇要进一
[前端开发中关于金额保留小数的问题](https://juejin.im/post/6876754864786014215)
[引申](https://juejin.im/post/6844904066418491406#heading-12)

## 20201220
+ 昨天看了一天的d2视频直播，听到的有些想法还是挺好的，感慨大厂还是挺强的。
+ 今天下午陪豆芽去没有花的径山花海去玩，还带了电脑改了会年终ppt;给妈妈打了几个电话都没接到，爸爸说妈妈身体不太好，还是有点担心。
+ 晚上看掘金看到个数组扁平化挺好玩的
```javascript
JS数组扁平化之简单方法实现
toString
const arr = [1, 2, 3, [4, 5, [6, 7]]];
const flatten = arr.toString().split(',');
优点：简单，方便，对原数据没有影响
缺点：最好数组元素全是数字或字符，不会跳过空位
join
const arr = [1, 2, 3, [4, 5, [6, 7]]];
const flatten = arr.join(',').split(',');
优点和缺点同toString
```

## 20211010
+ 去年年底换了部门，作为前端TL承担了更大的责任，也更忙了
+ 骚操作，可以在此基础上做二次封装，代替原来的生成uuid的方法，比如取几个用-拼接下
```javascript
// 看到比较好玩的，一行代码生成随机字符串 from 公众号前端印象 《JavaScript 奇怪又实用的姿势又增加了六个》
const str = Math.random().toString(36).substr(2, 10); 
/*
原理
先是 Math.random() 生成 [0, 1) 的数，也就是 0.123312 、 0.982931 之类的，然后调用 number 的 toString方法将其转换成36进制的，按照MDN的说法，36进制的转换应该是包含了字母 a~z 和 数字 0~9 的，因为这样生成的是 0.89kjna21sa 类似这样的，所以要截取一下小数部分，即从索引 2 开始截取10个字符就是我们想要的随机字符串了
*/
```
+ outline的冷知识
> 让元素有一个漂亮的边框，这行代码使用了CSS的outline属性。有一点你可能不知道，在CSS渲染的盒子模型（Box Model）中，outline并不会改变元素及其布局的位置。因此这比使用border属性要好得多

## 20220424
+ 疫情更严重了，居家办公两天
+ 最近在做http sdk2.0，对于axios的理解更深刻了，文件加密，二进制流
+ Vue.js设计与实现继续看起来
+ Vue.js设计与实现继续看起来

## 20220715
+ 早起2天了
+ 关于peerDependencies
```
peerDependencies按我理解适用的场景是类似vue或者react对应的插件场景，比如hooks，期望react是>16.8版本的。
期望主工程有，但是因为版本号问题，不会下载多份
dependecies里则会被安装,peerDependencies不会安装（不同Npm版本处理不一致，就像node_modules层级一样）
之前做http SDK Npm包时axios放在dependencies时是符合预期的，包本身会依赖axios，并且打包时是external出去的
但具体到项目使用，如果文档要求axios版本v0.21.2之后的版本，似乎在这个场景下放peerDependencies也不是不行，但是会增加使用者成本
毕竟现在还碰到一个问题没有解决，由于sdk依赖axios v0.21.2版本开始的拦截器runWhen，主工程dependecies中dependencies中axios版本安装低于该版本，如v0.19.2，那么产物中只会打包主工程中依赖的版本，导致异常，即使sdk中声明了axios依赖是v0.21.2之后的版本

参考：
https://juejin.cn/post/7007197855102287885
https://juejin.cn/post/6844904134248759309
```
