# learnFE
some essays on the way to be a FEer

## 在路上，永远热泪盈眶
## 陪着小豆芽一起成长

---

## 20200926
+ [【前端体系】从一道面试题谈谈对EventLoop的理解](https://juejin.im/post/6868849475008331783#heading-18)
+ 再温习了一遍eventloop
+ tips:
.then需要等状态确定后才能知道注册then还是catch，因此状态还没有确定之前下面的then中的回调都不会注册当异步任务中
finally无论状态有没有变都能够触发，因此会不依赖于状态改变注册

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
