# 2022-06-13 ~ 2022-06-19

## Review

[Reading Source Code: React-Query](https://alexkondov.com/reading-source-code-react-query/)

本文讲述了阅读React-Query源码时候对其思路的理解。

- React-Query这个库在目录结构上采用了前端开发所熟悉的结构，便于开发人员查阅。

- 这个库的思路是将功能拆分为core和react hooks，其中core采用面向对象的思路去编码，而react hooks则作为bridge工具，对外暴露简单易用的api。

- 它的hooks api用重载的实现，去迎合开发者们不同编码习惯的需求，这样开发者们在使用的时候去可以忽略默认唯一的参数签名了。

- 在源码中，该库将选项参数options当作类似于context的思路向下传递，可以避免参数签名过长带来的阅读难度，易于维护。

## Algorithm 1

[括号生成](https://github.com/JunwuHuang/leetcode-daily/blob/master/generate-parentheses/%E6%8B%AC%E5%8F%B7%E7%94%9F%E6%88%90.md)

## Algorithm 2

[删除链表的倒数第 N 个结点](https://github.com/JunwuHuang/leetcode-daily/blob/master/remove-nth-node-from-end-of-list/%E5%88%A0%E9%99%A4%E9%93%BE%E8%A1%A8%E7%9A%84%E5%80%92%E6%95%B0%E7%AC%AC%20N%20%E4%B8%AA%E7%BB%93%E7%82%B9.md)

## Tip

[The peculiar magic of flexbox and auto margins](https://css-tricks.com/the-peculiar-magic-of-flexbox-and-auto-margins/#:~:text=Setting%20the%20margin%20property%20on%20a%20flex%20child,the%20top.%20That%20last%20%E2%80%9Ctop%E2%80%9D%20should%20be%20%E2%80%9Cbottom%E2%80%9D)

在日常开发中，使用flex布局的时候经常会遇到类似这种的结果，前面的子节点都是flex-start，而最后一个节点希望它出现在最后面，但是在mdn的flex教程中并没有找到相关的内容

```html
<div class='parent'>
    <div class='child'>
    <div class='child'>
    <div class='child the-last-should-appear-in-the-end'>
</div>
```

但是写代码就是不断实践的过程，在看到这篇文章之前也发现了同样的解法，就是给最后一个子节点加上`margin-left: auto;`即可
