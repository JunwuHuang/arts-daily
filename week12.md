# 2022-08-08 ~ 2022-08-14

## Algorithm 1

[合并 K 个升序链表](https://github.com/JunwuHuang/leetcode-daily/blob/master/merge-k-sorted-lists/%E5%90%88%E5%B9%B6K%E4%B8%AA%E5%8D%87%E5%BA%8F%E9%93%BE%E8%A1%A8.md)

## Algorithm 2

[字母异位词分组](https://github.com/JunwuHuang/leetcode-daily/blob/master/group-anagrams/%E5%AD%97%E6%AF%8D%E5%BC%82%E4%BD%8D%E8%AF%8D%E5%88%86%E7%BB%84.md)

## Review

[Checking if a JavaScript native function is monkey patched](https://mmazzarolo.com/blog/2022-07-30-checking-if-a-javascript-native-function-was-monkey-patched/)

这篇文章介绍了如何检测原生 jsapi 是否被覆盖，其中有一个思路是当你拥有整个页面的完全控制权时，可以在页面的最前面去保留一个 api 的引用，然后后续通过全等号去判断前后 2 个引用地址是否相同来判断是否被覆盖了

```html
<html>
  <head>
    <script>
      // Store a reference of the original "clean" native function before any
      // other script has a chance to modify it.
      // In this case, we're just holding a reference of the original fetch API
      // and hide it behind a closure. If you don't know in advance what API
      // you'll want to check, you might need to store a reference to multiple
      // `window` objects.
      (function () {
        const { fetch: originalFetch } = window;
        window.__isFetchMonkeyPatched = function () {
          return window.fetch !== originalFetch;
        };
      })();
      // From now on, you can check if the fetch API has been monkey patched
      // by invoking window.__isFetchMonkeyPatched().
      //
      // Example:
      window.fetch = new Proxy(window.fetch, {
        apply: function (target, thisArg, argumentsList) {
          console.log("Fetch call intercepted:", ...argumentsList);
          Reflect.apply(...arguments);
        },
      });
      window.__isFetchMonkeyPatched(); // → true
    </script>
  </head>
</html>
```

起初看到这个方法的时候，想说 defineProperty 是否可以绕过，但是经尝试，是不可以的：

```javascript
(function () {
  const { fetch: originalFetch } = window;
  window.__isFetchMonkeyPatched = function () {
    return window.fetch !== originalFetch;
  };
})();

Object.defineProperty(window, "fetch", {
  get() {
    return 1;
  },
});
```

据此猜测`Object.defineProperty`是会改变原有属性的指针的，查阅 MDN 文档并没有找到相关介绍

> https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty

后面尝试了`Object.assign`，倒是可以成功绕过，但是没有想到如何利用该方法去注入恶意代码

```javascript
Object.assign(window.fetch, { a: 1 });
```

## Tips

[位运算符在 JS 中的妙用](https://juejin.cn/post/6844903568906911752)

最近在刷算法的时候发现了一些位操作符的妙用，搜了一下，有人整理了一些，其中也有我经常用的`~~4.2 ==> 4`这样的，最近学到的一个找到中间位置的操作是：

```javascript
var len = nums.length;
var mid = len >> 1;
```
