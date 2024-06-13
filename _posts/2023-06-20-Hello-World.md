---
title: Hello World!
date: 2023-06-20 16:06:00 +0800
categories: [随笔]
tags: [博客搭建, 随笔, Bug记录]
# pin: true
math: true
mermaid: true
# image:
#   path: /commons/devices-mockup.png
#   lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
#   alt: Responsive rendering of Chirpy theme on multiple devices.
---

## 引言

这一周终于开始重构个人博客了。

记得在大一的时候，某次上完离散数学，我无意中翻到了利用了 Github Pages 来搭建个人博客的文章，当时觉得挺有意思的，就跟着那篇教程一步一步的搭建了个基于 Hexo 的个人博客，当时是部署在 Github 赠送的个人域名上。再之后，由于博客维护麻烦+学业压力(雾)+三分钟热度，我没有继续维护更新，博客也就依旧停滞在时光中，保留着当时刚搭建完成的样子(乐)。

时至今日，大三的生活也基本结束了。在没有学业压力的大四生活(现在发现好像因为毕设白焦虑了一段时间,但总体而言大四挺自在的)中，打算让自己的生活更加充实、有趣一点。许多知乎、微信、小破站中收藏了但却一直以学业压力推脱而放着积灰的的视频、教程、项目、书籍等表项，也希望能在这一时间段内一点一点的解决处理完成~~(有点类似于放假前的复习规划啥的了)~~。于是在这几天的零碎时间内，把个人博客的基础布局搭了起来。

至于这个博客的作用嘛，现在的想法是一方面用于展示自己的部分信息，另一方面则是分享记录自己的工具学习、之前或之后遇到的，某些基本没有参考资料的 bug 的处理方法、平时做的一些事、某些想法以及可能有的极少数深夜 emo 时将所思所想流于笔下的产物~~(fei liao)~~.

以下大约就简单介绍下本博客的搭建及功能开发计划叭

## 博客搭建流程

### 功能开发计划

- [x] 模板获取与部署
- [x] ui、分享链接、个人信息的个性化
- [x] 百度/谷歌/必应搜索引擎收录申请
- [x] 部署启用评论系统
- [x] 在侧栏添加网易云音乐栏
- [x] 在右下角添加 live2d
- [x] 添加动态崩溃功能（
- [ ] To be continue...

#### 博客部署

最开始的时候，我参照了吴坎师兄的博客，也想要搭建一个简洁干净、以内容展示为主的博客。原本想基于吴坎师兄的博客模板进行修改的，但整着整着，我就意识到，我的需求跟师兄的模板匹配度并不算特别大，某些页面需要大改()，工作量略微有 yi 点点大。于是想找找看有没有其他符合需求的模板，挑的过程也是 Jekyll 框架的主题为主，因为看起来(和实际使用起来)其比 Hexo 框架好处理维护多了，最后挑中了 Chirpy 这款主题。由于考虑到需要对模板进行较大的修改，因此基于 fork 的方式获取了模板。最开始地时候，跟着模板中的教程一步步安装依赖并配置就可以完成一大半工作了。唔，至少呢，配置好后已经可以通过个人域名访问博客了。

#### ui、分享链接、个人信息的个性化

这一部分的内容主要是对模板的一些基础配置，包括但不限于：用户名、博客名、侧边栏的布局、头像的修改等。基本上修改都是针对 *.yml 文件进行的，修改起来也比较方便，按照模板中的注释修改即可。这里说一个小插曲，我用闲暇时间部署了两三天博客，7月2号时一切基本正常了，前两步都很顺利。结果3号早上，突然发现 Chirpy 模板有个版本更新，停用了一部分即将停止提供服务的插件(扶额.jpg)。考虑到博客还只是半成品，并且该更新确实有部分采用的价值，于是嘛，只能撤销更改，拉取最新的模板，参照旧版代码重新修改配置文件，好在一切都挺顺利。

#### 谷歌/必应搜索引擎收录申请

博客是部署成功了，但只有搜索引擎收录了，才能让其能在搜索引擎上作为搜索结果来源出现，从而使别人能发现并阅读。这就需要我们在搜索引擎上提交认证以及申请，通过后搜索引擎会通过爬虫定期爬我们的网站，并不定期收录。一般而言，验证方式有多种，包括直接在域名中添加 DNS 记录的网域认证，通过在网页中添加指定代码的网页认证等，为了方便起见，我都是通过 DNS 记录或者放置文件进行认证申请。

#### 部署启用评论系统

采用 giscus 作为评论系统的基础，根据摸索出来的教程。首先先去 giscus 官方主页，根据上面的需求填入创建仓库并填入对应的名字，之后将提供的代码中字段值填入自己的`_config.yml`文件中，最后设置`active: giscus`即可。

#### 添加网易云音乐栏

经过简单的外链播放器生成以及 css 样式的修改，成功地添加上了网易云音乐栏，本地测试也可以正常播放。只是说，实际效果跟理想效果有所出入，一方面风格不是很搭，另一方面在切换页面时会出现播放器重置的情况，这个问题还需要进一步解决。考虑到需求问题，暂时先将其注释隐藏了。如果有需要的话，可以在仓库源码`_includes/sidebar.html`中或者 F12 调出源码取消网易云播放器的注释以查看简单微调后的效果。

#### 添加 live2d

基于外链的 live-2d 部署比想象的简单。首先~~从[吴坎师兄的博客](https://wu-kan.cn/2019/01/18/%E5%9F%BA%E4%BA%8EJekyll%E6%90%AD%E5%BB%BA%E4%B8%AA%E4%BA%BA%E5%8D%9A%E5%AE%A2/#:~:text=%E7%BB%93%E6%9E%84%20%2DJekyll%E3%80%82-,%E5%8A%A0%E5%85%A5%20Live2D%20%E7%9C%8B%E6%9D%BF%E5%A8%98,-%E5%8F%82%E8%80%83%E4%BA%86%EF%BC%9A)那~~获取外链引入代码(),然后对于 Chirpy 主题，创建文件`_includes/live-2d.html`用来放置该代码，之后在`_layouts/default.html`中引入该文件就行啦~(实际使用时，发现这样子只能在本地测试才会显示live-2d，经过debug,参考[live2d-widget](https://github.com/stevenjoezhang/live2d-widget)的代码，经过一番尝试后，还是没解决bug，最后查看源码，终于发现原因。 github 生成页面时不同于本地生成，会压行，导致上述方法引入的界面会被压缩到一行，从而行注释符后的所有脚本都会注释掉😓)。之后的工作就是参照[参数文档](https://docs.paul.ren/pio/#/)以及 github 的模型仓库配置自己的 live-2d 了(忽然发现专业综合实践这门学分少事情多的课还是有那么一点用的)。顺带一提，为了让页面不冗余，我还注释掉了主题自带的回到页首小图标，有需要的小伙伴可以注释回去。模型收集自[imuncle/live2d](https://github.com/imuncle/live2d)。

![image-20230708221329424](https://s2.loli.net/2023/07/08/trVofP2QXUe3cHv.png){: width="972" height="589" }_我调了一下午 bug，最终才定位找到这😩_

#### 动态崩溃功能（

顾名思义，就是让用户切换窗口时让网站崩溃掉（。食用方法类似于 live-2d。找个地方把以下代码放进去就行了。参考自：[改变title if ···](https://www.cnblogs.com/norie/p/8143412.html)。
```html
<script>

(function() {
    var OriginTitile = document.title, titleTime;
    document.addEventListener('visibilitychange', function() {
        if (document.hidden) {
            document.title = 'Σ(っ °Д °;)っ哎呀，崩溃啦！';
            clearTimeout(titleTime);
        } else {
            document.title = '(/≧▽≦/)咦！又好了！|' + OriginTitile;
            titleTime = setTimeout(function() {
                document.title = OriginTitile;
            },1500);
        }
    });
})();
    
</script>
```

### 部署中遇到的一部分问题以及解决方法

#### 1. linux 系统中 node.js 版本过低

在根据教程安装依赖的时候，由于 node.js 的版本过低，会导致弹出大量警告。解决方法是先将仓库代码回退到修改前，并升级 node.js 版本，之后重新安装依赖。linux 系统下的部分相关指令如下：

```bash
# 清除缓存信息
npm cache clean -f 
# 下载node安装包
npm install -g n 
# 升级到nodejs最新稳定版本
n stable 
# 查看当前版本
node -v
# 更新npm 注意要确保node先更新，避免依赖出错
npm install -g npm
```

#### 2. 下载过慢或无法下载

由于网络环境的原因，`n stable` 可能出现一直不显示下载条或下载过慢的情况，由于该命令不走系统代理，我采用的方案是使用 proxychains 工具让其强制走代理(瞬间起飞！)。proxychains 工具十分好用与方便，经过几天的使用，现在我基本上遇见网络问题都下意识地想用它()，至于具体使用教程可以参考我的另一篇文章(TODO)。

