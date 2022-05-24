# 20220-05-23 ~ 2022-05-29

## Algorithm

[两数相加](https://github.com/JunwuHuang/leetcode-daily/blob/master/add-two-numbers/%E4%B8%A4%E6%95%B0%E7%9B%B8%E5%8A%A0.md)

## Review

[What the useEvent React hook is (and isn't)](https://typeofnan.dev/what-the-useevent-react-hook-is-and-isnt/)

### 评论

- 文中列出了两种经典场景，在当今没有 useEvent 的环境下处理起来会比较硌手
  1. onClick 的 handler 在每次 render 下都会重新定义，导致组件无法利用 memo 优化
  2. 组件数据在多 deps 初始化的情况下会触发多次
- 关于 solidjs 的 createEffect 的想法
  - 更多的 lifecycle 可能会加重使用者的心智负担，就像过去的 class component

## Tip

这个方法在未来会加入到 react 提供的 hook api 中，但是团队的 react 版本不会那么轻易升级，那么可以把以下代码加入到现有项目中，就能享用了。

[useEvent implementation](https://github.com/reactjs/rfcs/blob/useevent/text/0000-useevent.md#internal-implementation)

```
// (!) Approximate behavior

function useEvent(handler) {
  const handlerRef = useRef(null);

  // In a real implementation, this would run before layout effects
  useLayoutEffect(() => {
    handlerRef.current = handler;
  });

  return useCallback((...args) => {
    // In a real implementation, this would throw if called during render
    const fn = handlerRef.current;
    return fn(...args);
  }, []);
}
```

## Algorithm

[无重复字符的最长子串](https://github.com/JunwuHuang/leetcode-daily/blob/master/longest-substring-without-repeating-characters/%E6%97%A0%E9%87%8D%E5%A4%8D%E5%AD%97%E7%AC%A6%E7%9A%84%E6%9C%80%E9%95%BF%E5%AD%90%E4%B8%B2.md)
