# 2022-08-15 ~ 2022-08-21

## Algorithm 1

[合并区间](https://github.com/JunwuHuang/leetcode-daily/blob/master/merge-intervals/%E5%90%88%E5%B9%B6%E5%8C%BA%E9%97%B4.md)

## Algorithm 2

[跳跃游戏](https://github.com/JunwuHuang/leetcode-daily/blob/master/jump-game/%E8%B7%B3%E8%B7%83%E6%B8%B8%E6%88%8F.md)

## Review

[How and why we removed jQuery from GOV.UK](https://insidegovuk.blog.gov.uk/2022/08/11/how-and-why-we-removed-jquery-from-gov-uk/)

该文分享了英国政府官网是怎么去移除jq的以及背后的原因。

#### 需求背景

其中作为产品需求的核心是：作为国家政府官网，面向的用户群体是不限的，所以可能用户的网速会很慢、设备配置也可能会很低。

那么在引入了32kb的jq的情况下，事实上又没有完全去使用它，就会浪费了相当一部分的资源，于是才有这样的优化需求。

#### 实施方案

另外，在实现方案中，考虑到有一些后端开发也用到了jq，但是他们可能不太熟悉js以至于不知道怎么做，那么前端开发需要整理一份操作手册去指导后端如何移除jq。

#### 发布策略

发布阶段没有莽撞的直接移除旧的jq，是因为其他子程序可能还未更新到移除jq的版本。而当所有的子程序移除了对jq的依赖，那么再发布移除了jq的版本。



## Tips

[在 React 中为什么要用 JSX](https://juejin.cn/post/7132472958051680287)

js 的语法扩展（需利用 babel 编译），让组件的布局结构看起来更清晰明了。

题外话：对比 flutter 的布局写法的话，jsx以类似xml格式的形式编写，会让结构看起来更清晰

```JSX
<Scaffold
    appBar={
        <AppBar>title</AppBar>
    }
>
    <Center>
        body
    </Center>
</Scaffold>
```

```dart
Scaffold(
    appBar: AppBar(
        title: Text('title')
    ),
    body: Center(
        child: Text('body')
    )
)
```
