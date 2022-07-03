# 2022-06-27 ~ 2022-07-03

## Review

[When You Should Prefer Map Over Object In JavaScript](https://www.zhenghao.io/posts/object-vs-map)

这篇文章介绍了Map和Object的区别，也介绍了在V8加持下，它们在不同场景下的性能区别；总的来说，如果你只是想要一个hash map，那么就建议使用Map。

## Tip

[ES2022新特性：Object.hasOwn()](https://ost.51cto.com/posts/10066)

此前要判断某个key是否存在于Object中的需要写一大串代码: {}.hasOwnProperty.call(target, key)

这次带来的新特性可以减少很多代码，如果要实现一个polyfill的话，大致是这样：

```javascript
function hasOwn(target, key) {
    return Object.prototype.hasOwnProperty.call(target, key)
}
```

## Algorithm 1

[子集](https://github.com/JunwuHuang/leetcode-daily/blob/master/subsets/%E5%AD%90%E9%9B%86.md)

## Algorithm 2

[全排列](https://github.com/JunwuHuang/leetcode-daily/blob/master/permutations/%E5%85%A8%E6%8E%92%E5%88%97.md)
