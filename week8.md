# 2022-07-11 ~ 2022-07-17

## Algorithm 1

[搜索旋转排序数组](https://github.com/JunwuHuang/leetcode-daily/blob/master/search-in-rotated-sorted-array/%E6%90%9C%E7%B4%A2%E6%97%8B%E8%BD%AC%E6%8E%92%E5%BA%8F%E6%95%B0%E7%BB%84.md)

## Algorithm 2

[旋转图像](https://github.com/JunwuHuang/leetcode-daily/blob/master/rotate-image/%E6%97%8B%E8%BD%AC%E5%9B%BE%E5%83%8F.md)

## Review

[Using the native web share JavaScript API](https://daily-dev-tips.com/posts/using-the-native-web-share-javascript-api/)

以前想要实现分享功能都要借助bridge去调用原生App的api，现在浏览器也有标准的分享api了，目前仅在一些比较新的浏览器上支持，详细请参考caniuse

## Tip

[visibilitychange](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/visibilitychange_event)

最近需要用到这个事件，仔细查阅可以发现有这么一些注意事项：

1. 当 visibleStateState 属性的值转换为 hidden 时，Safari 不会按预期触发visibilitychange； 因此，在这种情况下，您还需要包含代码以侦听 pagehide 事件。
1. 该事件应属于document的，旧版本safari无法通过window去监听
