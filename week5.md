# 2022-06-20 ~ 2022-06-26

## Review

[AbortController is your friend](https://whistlr.info/2022/abortcontroller-is-your-friend/)

本文讲述了AbortController的使用场景，除了在fetch的时候可以使用，在注册监听事件的时候也可以使用；作者还介绍了如何去封装一些工具以投入生产，例如在react的useEffect下使用，以便在消除副作用的环节中去执行abort

## Algorithm 1

[下一个排列](https://github.com/JunwuHuang/leetcode-daily/blob/master/next-permutation/%E4%B8%8B%E4%B8%80%E4%B8%AA%E6%8E%92%E5%88%97.md)

## Algorithm 2

[组合总和](https://github.com/JunwuHuang/leetcode-daily/blob/master/combination-sum/%E7%BB%84%E5%90%88%E6%80%BB%E5%92%8C.md)

## Tip

[「译」ES 2021 新特性: Top-level await | 掘金技术征文-双节特别篇](https://juejin.cn/post/6878441223951122446)

最近es2022正式发布了，其中有一个特性就是本文介绍的top-level await，它的使用场景便是一些需要初始化的模块，例如在webview中需要初始化js bridge抑或是在接入一些例如应用监控平台的sdk大多时候都需要去初始化。以往的时候我们可能需要的在引入该模块的时候再去执行初始化，例如：

```javascript
// module
export const initSdk = async () => {
    return await window.__SDK__.getInstance()
}
```

```javascript
import {initSdk} from './module'

initSdk().then(instance => {
    // doSomething
})
```

但是有的时候，相关sdk是希望提前准备的，比如在引入的时候就先初始化，点击按钮的时候可以直接触发调用。这种场景下，top-level await就可以派上用场了
