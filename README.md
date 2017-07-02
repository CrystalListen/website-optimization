## 网站性能优化项目

本次练习基于以下链接中的项目进行优化：
https://raw.githubusercontent.com/udacity/cn-frontend-development-advanced/master/Website%20Optimization_zh.zip

### 优化目标：
1. index.html 的 PageSpeed Insights得分高于90
2. view/pizza.html在滚动时保持60FPS的帧速
3. view/pizza.html在调整pizza大小的时间小于5毫秒

### 如何启动

```bash
  $> cd /你的工程目录
  $> python -m SimpleHTTPServer 8080
```

1. 打开浏览器，访问 localhost:8080
2. 下载 [ngrok](https://ngrok.com/) 并将其安装在你的工程根目录下，让你的本地服务器能够被远程访问。

``` bash
  $> cd /你的工程目录
  $> ./ngrok http 8080
```
### 优化方法
1. 调整images/pizzeria.jpg尺寸为100*75
2. 压缩图片
3. Google字体同步加载，使用七牛源
4. CSS非阻塞加载
5. 使用getElementById替代querySelector
6. updatePosition中使用transform替代left属性
7. requestAnimationFrame代替动画效果
8. 使用DocumentFragment绘制披萨
9. 使用Range和DocumentFrame克隆修改DOM样式调整pizza大小的时间小于5毫秒
10. 减少pizza个数

### 一些关于优化的提示与诀窍
* [web 性能优化](https://developers.google.com/web/fundamentals/performance/ "web 性能")
* [分析关键渲染路径](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "分析关键渲染路径")
* [优化关键渲染路径](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html "优化关键渲染路径！")
* [避免 CSS 渲染阻塞](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html "css渲染阻塞")
* [优化 JavaScript](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript.html "javascript")
* [通过 Navigation Timing 进行检测](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp.html "nav timing api")。在前两个课程中我们没有学习 Navigation Timing API，但它对于自动分析页面性能是一个非常有用的工具。我强烈推荐你阅读它。
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads.html">下载量越少，性能越好</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer.html">减少文本的大小</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization.html">优化图片</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching.html">HTTP缓存</a>

### 使用 Bootstrap 并定制样式
这个项目基于 Twitter 旗下的 <a href="http://getbootstrap.com/">Bootstrap框架</a> 制作。所有的定制样式都在项目代码库的 `dist/css/portfolio.css` 中。

* <a href="http://getbootstrap.com/css/">Bootstrap CSS</a>
* <a href="http://getbootstrap.com/components/">Bootstrap组件</a>

### 更新记录
* 1. 修复调用changePizzaSizes时，pizza大小没有改变的问题
* 2. 优化index.html中CSS阻塞的问题