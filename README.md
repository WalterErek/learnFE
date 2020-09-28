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
