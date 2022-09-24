# 2022-09-19 ~ 2022-09-25

## Algorithm 1

[单词拆分](https://github.com/JunwuHuang/leetcode-daily/blob/af79db10aa53b00c0052f2531ea399dccd26369b/word-break/%E5%8D%95%E8%AF%8D%E6%8B%86%E5%88%86.md)

## Algorithm 2

[最小栈](https://github.com/JunwuHuang/leetcode-daily/blob/2074c8e8470505890621f66a3e4f4f6220f8ef17/min-stack/%E6%9C%80%E5%B0%8F%E6%A0%88.md)

## Review

[Secure Your Node.js App with JSON Web Tokens](https://blog.appsignal.com/2022/09/14/secure-your-nodejs-app-with-json-web-tokens)

本文是关于如何在nodejs中使用jwt的教程，其中对于JWT_SECRET的处理利用了dotenv工具，并且也强调了不应该将它公开出去

## Tips

[H5 向 微信小程序 的即时通讯“解决方案”](https://github.com/RedTeapot/WxMiniProgramHybrid)

该工具是针对于小程序中的webview的bindmessage使用限制做的绕行的方案，该api的限制条件为：小程序后退、组件销毁、分享；这样的话，基本就告别了即时通讯了，所以该api使用了onload去接收参数的特性做了绕行方案。首先是小程序方面新建一个中间页面用于处理通讯消息，该页面需要设置一个“处理中”的交互，然后利用路由栈获取到webview所在的页面，去改变webview的链接的hash，webview则利用hashchange去做文章。

该方法在体验上肯定是不够友好的，所以当产品决策上可以避免这样的操作，当然是最好的了。
