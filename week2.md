# 20220-05-30 ~ 2022-06-05

## Tip

SPA 对于路由的处理方式主要依赖 hisotryState API,；在一些不需要 Vue/React 框架的场景下，想要简易实现 SPA 的路由体验，可参考这段代码去处理。

[Implements React Routing in Plain React, without reliance on React-Router or any other libraries.](https://github.com/ashok-khanna/react-snippets/blob/main/Router.js)

```
/* Code Starts Here */

import React from 'react';
import { useEffect, useState } from 'react';

// Global Event Listener on "click"
// Credit Chris Morgan: https://news.ycombinator.com/item?id=31373486
window.addEventListener("click", function (event) {
    // Only run this code when an <a> link is clicked
    const link = event.target.closest("a");
    // Correctly handle clicks to external sites and
    // modifier keys
    if (
        !event.button &&
        !event.altKey &&
        !event.ctrlKey &&
        !event.metaKey &&
        !event.shiftKey &&
        link &&
        link.href.startsWith(window.location.origin + "/") &&
        link.target !== "_blank"
    ) {
        // prevent full page reload
        event.preventDefault();
        // Main routing function
        navigate(link.href);
    }
});

/* Main Component */

export default function Router ({routes, defaultComponent}) {

    // state to track URL and force component to re-render on change
    const [currentPath, setCurrentPath] = useState(window.location.pathname);

    useEffect(() => {
        // define callback as separate function so it can be removed later with cleanup function
        const onLocationChange = () => {
            // update path state to current window URL
            setCurrentPath(window.location.pathname);
        }

        // listen for popstate event
        window.addEventListener('popstate', onLocationChange);

        // clean up event listener
        return () => {
            window.removeEventListener('popstate', onLocationChange)
        };
    }, [])
    return routes.find(({path, component}) => path === currentPath)?.component || defaultComponent
}

/* Use the below in buttons and programmatically to navigate to pages */

export function navigate (href) {

    // update url
    window.history.pushState({}, "", href);

    // communicate to Routes that URL has changed
    const navEvent = new PopStateEvent('popstate');
    window.dispatchEvent(navEvent);
}
```

## Algorithm

[最长回文子串](https://github.com/JunwuHuang/leetcode-daily/blob/master/longest-palindromic-substring/%E6%9C%80%E9%95%BF%E5%9B%9E%E6%96%87%E5%AD%90%E4%B8%B2.md)

## Review

[5 Awesome API for your Projects!](https://medium.com/codex/5-awesome-api-for-your-projects-cc61c795ac39)

这篇帖子分享了 5 个免费开放 api，对我来说它们分别提供了几类测试数据：

1. 用户信息
1. 媒体数据
1. 天气预报
1. FAQ
1. 图标

> 在前端开发的学习路上经常会遇到的问题就是，没有数据来展示，怎么办？

我以往的经验是自己写一些[简单的 api ](https://github.com/JunwuHuang/learn-restify)供我自己去使用，但现在，如果网络环境不是问题的话，可以利用这篇文章分享的 api 去和前端代码关联起来

## Algorithm

[盛最多水的容器](https://github.com/JunwuHuang/leetcode-daily/blob/master/container-with-most-water/%E7%9B%9B%E6%9C%80%E5%A4%9A%E6%B0%B4%E7%9A%84%E5%AE%B9%E5%99%A8.md)
