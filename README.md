# TISP
## A small and convenient blog program.<br>一个小巧方便的博客程序。

特点：  
- 无需动态程序渲染，纯静态
- 文章以 md 后缀存放，实时写作，实时显示
- 存放 md 文件的地方不限，只要允许被跨域访问即可
- 使用 PAJX 加载文章，更快~~（对比WP）~~，更流畅，更方便


当然，TISP 作为一个刚诞生的程序，也有许多缺点：
- 目前不支持 RSS  
- 在没有 php 环境支持时，每增加一篇文章就需要手动更（c)改（v) article.json 中的内容 
- 为 TISP 开发主题不会太容易

## 下载
去 release 页面下载，下载完成解压后的 index.html 就是。

**最新测试** 版：使用下载工具下载这个页面：<http://tyatt.top/index.html>

## DEMO
<http://tyatt.top/index.html> 或 <http://tyatt.top/>

## 注意
请在下载完成后更改 “按照提示设置博客基本信息” 部分的变量的值来自定义网站，请用http或https协议访问index.html！

## 原理
JS 通过 URL 的查询部分判断应该显示什么内容，并用 AJAX 读取对应的 md 文件，渲染，显示到页面上。跳转部分使用 PJAX。页面初始化时使用 switch 判断？后面的内容并调用特定 JS 函数，PJAX 跳转时则是直接调用特定函数。

## 部分配置文件
article.json
```javascript
[
    {
        "title": "Hello World！",//显示出的文章标题
        "link": "helloworld",//md文件夹内对应markdown文件的文件名，不包含 “.md” 
        "time": "1111-01-01",//写作时间，格式如示例
        "cate": "test",//分类，暂时没有实质作用，但会显示在首页的文章列表以及文章页的合适位置
        "titpiclink": false,//题图链接，请使用img标签可以展示的格式，没有请填false
        "titbclr": "#2196f3",//如果“titpiclink”为false，此项生效，设置的是题图区域的背景颜色
        "titfclr": "#fff"//如果“titpiclink”为false，此项生效，设置的是题图区域的字体颜色
    }
]
```
> 用之前记得删掉压缩包里 article.json 内的所有注释

## 注意  
这只是我一时兴起做出来的一个小程序，我不能保证它未来会 停更 or 随缘更新 or 成为一个正式项目。  
