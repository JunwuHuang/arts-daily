# 2022-09-12 ~ 2022-09-18

## Algorithm 1

[单词搜索](https://github.com/JunwuHuang/leetcode-daily/blob/master/word-search/%E5%8D%95%E8%AF%8D%E6%90%9C%E7%B4%A2.md)

## Algorithm 2

[柱状图中最大的矩形](https://github.com/JunwuHuang/leetcode-daily/blob/master/largest-rectangle-in-histogram/%E6%9F%B1%E7%8A%B6%E5%9B%BE%E4%B8%AD%E6%9C%80%E5%A4%A7%E7%9A%84%E7%9F%A9%E5%BD%A2.md)

## Review

[TIL: You Can Access A User’s Camera with Just HTML](https://austingil.com/html-capture-attribute/)

本篇文章介绍了移动端html的一个调用摄像头的功能，通过给type为file的input控件设置capture属性去实现，目前的兼容情况不是很好，不过这真的食一项很好的用户体验提升点，不用借助于原生app的sdk就能实现调用摄像头；这里也提到了该功能并不需要询问用户的调用权限，有网友会担心这样会带来安全风险，而作者并不这么认为，因为最终数据流还是在本地，只要表单不提交，那么数据就还是在本地，而剩下的安全问题跟以往的表单方面的问题食一样的。此前在做身份证ocr功能的时候有尝试过，该功能的体验还是不错的。

## Tips

[说说 Vue3 的 watchEffect 与 React Hooks 的 useEffect](https://geylnu.com/2020/10/10/%E8%AF%B4%E8%AF%B4Vue3%E7%9A%84watchEffect%E4%B8%8EReact-Hooks%E7%9A%84useEffect/)

此前vue3的一次实践中，对于watchEffect不是很理解，这篇文章介绍了它与react中的useEffect的一些细节上的区别，可以帮助react使用者去更好的理解watchEffect
