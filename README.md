# Hexo theme : Snippet

Snippet is concise and simple hexo theme, that you may have been looking for for a long time!

If you love the theme, please show your support by [Staring](https://github.com/madc0de/hexo-theme-snippet/stargazers) it.

[![Build Status](https://www.travis-ci.org/shenliyang/hexo-theme-snippet.svg?branch=master)](https://www.travis-ci.org/madc0de/hexo-theme-snippet)
[![Read the Docs](https://img.shields.io/badge/docs-complete-brightgreen)](https://github.com/madc0de/hexo-theme-snippet/blob/master/README.md)
[![HitCount](http://hits.dwyl.io/shenliyang/hexo-theme-snippet.svg)](http://hits.dwyl.io/madc0de/hexo-theme-snippet)
[![mnt-image](https://img.shields.io/maintenance/yes/2019.svg)](../../commits/master)
[![codebeat badge](https://codebeat.co/badges/6ef2dcd2-af90-40e0-9628-ac689441f774)](https://codebeat.co/projects/github-com-shenliyang-hexo-theme-snippet-master)
[![GitHub stars](https://img.shields.io/github/stars/madc0de/hexo-theme-snippet.svg)](https://github.com/madc0de/hexo-theme-snippet/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/madc0de/hexo-theme-snippet.svg)](https://github.com/madc0de/hexo-theme-snippet/network)
[![hexo version](https://img.shields.io/badge/hexo-%3E%3D%203.0-blue.svg)](http://hexo.io)
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/madc0de/hexo-theme-snippet/blob/master/LICENSE)


[主题Demo戳这里](http://shenliyang.github.io?rf=gh-demo)

![hexo-theme-snippet](https://d33wubrfki0l68.cloudfront.net/763823edc0bbea422cf3d04a3b7f49673a295baf/611b4/themes/screenshots/asnippet@2x.jpg "Snippet Theme")


## Theme Features

- [x] Native JavaScript implementation of jQuery on the go.
- [x] Style supports CSS preprocessor Less for easy theme customization
- [x] Article expiration reminder
- [x] Website announcement function
- [x] Homepage image lazy loading
- [x] Home article thumbnails Automatically retrieved from pictures in articles (support for random pictures)
- [x] Responsive Theme (Mobile First)
- [x] Support 3D Cloud Tags
- [x] Support article push and article reward
- [x] Local search and Google search
- [x] Support for multiple third-party comment systems
- [x] Support website statistics and non-garlic visitors statistics
- [x] Simple design on mobile
- [x] Support code highlighting and support custom highlight styles
- [x] Supports Shell Script to automate Hexo blog deployment via Travis CI
- [x] Support Hexo automated deployment results to send emails and real-time push to nails



# **Basic Articles**

> If you were using lower than Hexo 2.x, in order to avoid unknown errors, please back up your data or create a new blog directory.

> "Theme Directory" => `themes\hexo-theme-snippet`
> "Hexo Root Directory" =>`Project home directory`
> "Theme Configuration" => `themes\hexo-theme-snippet\_config.yml`
> "Hexo Configuration" => `_Config.yml` in the project's home directory

### 1. Environment Setup

需要`Node.js` 环境、`Git` 环境以及 `Hexo` ,如果你尚未安装或者不了解 `Hexo`，请参考 [官方教程](https://hexo.io/zh-cn/docs/index.html) 进行了解以及安装。如果需要构建工具请自行安装，或使用本主题的Gulp方式。


### 2. Theme Download

有两种方式获取本主题--下载 `*.zip` 文件和通过 `git`方式：

1. 下载 [Snippet主题](https://github.com/shenliyang/hexo-theme-snippet) 文件解压后放在 `themes` 目录下，和博客中的landscape为同级目录

2. Git方式，在Hexo根目录执行：
``` bash
git clone git://github.com/shenliyang/hexo-theme-snippet.git themes/hexo-theme-snippet
```

### 3. Install Theme Plugin

因为 **hexo-theme-snippet** 使用了 `ejs` 模版引擎 、 `Less` CSS预编译语言以及在官方插件的基础上
进行功能的开发，以下为必装插件：

``` bash
npm i hexo-renderer-ejs hexo-renderer-less hexo-deployer-git -S
```

### 4. Theme Deployment

> 如果没有更改过主题源文件,也不需要代码优化可以跳过1,2,3步骤


1. gulp打包构建，拷贝主题目录下`package.json`文件到Hexo根目录下，然后安装项目的开发依赖。  [Gulp入门指南](http://www.gulpjs.com.cn/docs/getting-started/)
``` bash
npm i   //安装项目依赖
```

2. 在Hexo根目录下创建一个名为 gulpfile.js 的文件：
``` bash
require('./themes/hexo-theme-snippet/gulpfile');
```

3. 运行 gulp：
``` bash
gulp 或者 gulp default   //执行打包任务
```

4. 清空hexo静态文件和缓存，并重新生成
``` bash
hexo clean && hexo g  //清空缓存并生成静态文件
```

5. 本地预览，确没有问题再进行发布
``` bash
hexo s -p 4000 或者 hexo s  //启动本地服务默认
```

6. 当gulp执行完成，并提示  `please execute： hexo d` 时，可以进行发布
``` bash
hexo d 或者 gulp deploy  //部署发布
```

### 5. Theme Updating

The theme may be optimized and updated from time to time, update the theme code using below commands.

``` bash
cd themes/hexo-theme-snippet
git pull
```

# **Topic**

### 1. Theme Configuration

``` yaml

## menu -- 导航菜单显示{[@page:名字,@url:地址,@icon:图标]}
menu:
  - page: home
    url: /
    icon: fa-home

## favicon -- 网站图标位置{@favicon}
favicon: /favicon.ico

## rss --rss文件位置{@rss}
rss: /atom.xml


# 各个小工具的设置

## widgets -- 6个左边小工具{@widgets:[notification,category,archive,tagcloud,friends]}
widgets:
  - search
  - notification
  - social
  - category
  - archive
  - tagcloud
  - friends

# 各个小工具的设置

## 搜索
jsonContent:
  searchLocal: true // 是否启用本地搜索
  searchGoogle: true //是否启用谷歌搜索
  posts:
    title: true
    text: true
    content: true
    categories: false
    tags: false

## notification config --网站公告设置,支持 html 和 纯文本
notification: |-
            <p>主题已经上线！欢迎下载或更新~ <br/>
            主题下载：<a href="https://github.com/shenliyang/hexo-theme-snippet" title="fork me" target="_blank">Snippet主题</a> <br/>
            <hr/>接受贡献，包括不限于提交问题与需求，修复代码。欢迎Pull Request<br/>支持主题：<a href="https://github.com/shenliyang/hexo-theme-snippet/stargazers">Star一下</a></p>

## 社交设置{@name:社交工具名字，@icon:社交工具图标，@href:设置工具链接} [参考图标](http://fontawesome.io/icons/)
social:
  - name: Github
    icon: git
    href: //github.com/shenliyang

## 文章分类设置{@cate_config:{@show_count:是否显示数字，@show_current: 是否高亮当前category}}
cate_config:
   show_count: true
   show_current: true

## 文章归档设置{@arch_config:/*参数参考：https://hexo.io/zh-cn/docs/helpers.html#list-archives*/}
## 推荐组合方式：[{type: 'monthly',format: 'YYYY年MM月'},{type: 'yearly',format: 'YYYY年'}]
arch_config:
   type: 'monthly'
   format: 'YYYY年MM月'
   show_count: true
   order: -1

## 标签云设置{/*参数参考：http://www.goat1000.com/tagcanvas-options.php */}
tagcloud:
  tag3d: false // 是否启用3D标签云
  textColour: '#444' // 字体颜色
  outlineMethod: 'block' // 选中模式(outline|classic|block|colour|size|none)
  outlineColour: '#FFDAB9' // 选中模式的颜色
  interval: 30 // 动画帧之间的时间间隔，值越大，转动幅度越大
  freezeActive: true // 选中的标签是否继续滚动
  frontSelect: true // 不选标签云后部的标签
  reverse: true // 是否反向触发
  wheelZoom: false // 是否启用鼠标滚轮

## 友链设置{@链接名称：链接地址{@links:[,,,]}}
links:
  - Hexo官网: https://hexo.io/zh-cn/


# 主题自定义个性化配置

## 网站宣传语{@branding：网站宣传语(不设置显示本地图片)}
branding: 从未如此简单有趣

## 设置banner背景图片{@img:自定义图片地址(支持绝对和相对路径),主题默认{"静态背景":"banner.jpg"},{"动态背景":"banner2.jpg"},{"动态星空背景":"banner3.jpg"}}
## 例如：http://snippet.shenliyang.com/img/banner|2|3.jpg, 或者 './img/banner-img.jpg'(相对本地资源地址)
banner:
  img: http://snippet.shenliyang.com/img/banner.jpg


## 设置carousel{@img:图片地址,@url:点击跳转链接(默认值:"javascript:")}
carousel:
  img: 'img/head-img.jpg'
  url: 'javascript:'

## 首页列表底部面板{@homePanel: 是否开启}
homePanel: true

## 首页文章列表缩略图
### 加载规则: 自定义文章缩略图(在Front-matter中添加的'img'字段) > 文章内的图片 > defaultImgs(随机获取) > 无图模式列表

## 自定义随机图片
defaultImgs:
  - http://www.example.jpg //远程图片链接示例
  - /img/default-1.jpg //本地图片链接示例

### 文章摘要{@摘要显示优先级：自定义摘要 > 自动截取摘要 }
### 自定义摘要范围{@<!--more-->:截取more之前的内容为摘要}
### 自动截取摘要{@excerptLength:自动截取文章前多少个字为摘要，不配置默认：120字}
excerptLength: 120

## 是否开启文章目录
toc: true

## 代码高亮配置{@highlightTheme: 主题名称,(配置暂时不可用，后续开发中…)}

highlightTheme: default //TODO

## 文章过期提醒功能 {@warning:{days:临界天数(默认300天,设置0关闭功能),text:提醒文字/*%d为过期总天数占位符*/}}
warning:
  days: 300
  text: '本文于%d天之前发表，文中内容可能已经过时。'

## 文章内声明{@declaration: {enable:是否开启,title:声明标题,tip:提示内容}}
declaration:
  enable: true
  title: '转载声明'
  tip: |-
      商业转载请联系作者获得授权,非商业转载请注明出处 © <a href="" target="_blank">Snippet</a>

## 文章打赏{@reward: {alipay:支付宝打赏,wepay:微信打赏,tip:打赏提示语; 链接都为空,关闭打赏功能}}
reward:
  alipay: ''
  wepay: '../img/reward-wepay.jpg'
  tip: 赞赏是不耍流氓的鼓励


## 主题评论

### gitment
gitment:
  enable: false
  owner:
  repo:
  client_id:
  client_secret:
  labels:
  perPage:
  maxCommentHeight:

### 来必力(默认选项)
livere:
  enable: true
  livere_uid:

### 友言评论(服务不稳定，经常无法加载)
uyan:
  enable: false
  uyan_id:

### Disqus评论(需要翻墙，或者搭建代理)
disqus:
  enable: false
  shortname: snippet
  count: false

### 畅言评论(需要ICP备案)
changyan:
  enable: false
  appid:
  conf:

### Valine评论 参考网站: [valine评论](https://valine.js.org/)
valine:
  enable: true
  appId:
  appKey:
  placeholder: 说点什么吧
  notify: false // 邮件通知
  verify: false // 验证码
  avatar: mm // avatar头像
  meta: nick,mail // 输入框内容，可选值nick,mail,link
  pageSize: 10

## Gitalk评论 参考网站: [一个基于Github Issue和Preact开发的评论插件](https://gitalk.github.io/)
gitalk:
   enable: false
   clientID: "" // Github 应用ID
   clientSecret: "" // Github 应用密钥
   repo: shenliyang.github.io // Github仓库地址
   owner: shenliyang  // Github 用户名(Github仓库拥有者)
   admin: shenliyang // GitHub repository 的所有者和合作者 (对这个 repository 有写权限的用户)可以有一个或多个，如果有多名可使用，例如：admin: admin1,admin2 配置
   perPage: 10 // 每次加载的数据大小，最多100
   distractionFreeMode: true // 是否启用无干扰模式，类似Facebook评论框的全屏遮罩效果

   // 以下参数主题会默认处理，不需要配置
   language // 语言类型，默认为站点配置中选项
   id // 页面的唯一标识, 已使用md5对pathname转换生成唯一id处理

## 网站访客统计 [不蒜子统计](http://busuanzi.ibruce.info/)
visit_counter:
   site: true // 总访问量和访问人数统计
   page: true // 文章阅读量统计

## 网站访问统计

### 网盟CNZZ统计 参考网站: [网盟CNZZ](http://www.umeng.com/)
cnzz_anaylytics:

### 百度统计 参考网站: [百度统计](https://tongji.baidu.com/)
baidu_anaylytics:

### 谷歌统计 参考网站：[谷歌统计](https://www.google-analytics.com/)
google_anaylytics:

### 腾讯分析 参考网站：[腾讯分析](http://ta.qq.com/)
tencent_analytics:

### 百度站点认证
baidu-site-verification:

### 百度自动推送(@baidu_push: 是否启用百度自动推送)  参考网站: [百度站长资源](https://ziyuan.baidu.com/college/courseinfo?id=267&page=2#h2_article_title18)
baidu_push:

## ICON配置 (不配则启用本地Font Icon)
fontAwesome: //cdn.bootcss.com/font-awesome/4.7.0/css/font-awesome.min.css

## 网站主题配置
since: 2017  //建站时间
beian: '京ICP备04000001号' //网站备案号
robot: 'all'  //控制搜索引擎的抓取和索引编制行为，默认为all
version: 1.2.1  //当前主题版本号
```

### Theme skills usage and function expansion
1. 修改新增文章Front-matter模板,修改`scaffolds`目录下的`post.md`模板
> 模板文件内部不要保留注释部分,关键词后面请使用英文冒号
``` yml
  ---
  title: {{ title }} // 标题
  date: {{ date }}   // 时间
  categories: ['分类1','分类2'] // 分类
  tags: ['标签1','标签2']       // 标签
  comments: false    // 是否开启评论
  img:               // 自定义缩略图
  ---
```

2. Enable local search within the site

If you want to use local site search, you must install the plugin **hexo-generator-json-content** to create a local search json file
```bash
npm i hexo-generator-json-content --save
```
Then modify the `jsonContent` related parameters under theme configuration _config.yml.

# **Ascension**

## 1. Travis CI Introduction
CI stands for Continuous Integration System. For individuals, it means that your code is submitted to the remote (here is GitHub), and it is automatically compiled, tested, and deployed automatically.

There is no need to worry about replacing the computer, but also to re-deploy the environment. As long as you can push articles to the remote, other things can be left to Travis CI for processing.

## 2. Travis CI usages

> 默认前提是已经通过Github进行授权登录Travis网站，并关联了GitHub上的仓库和相关配置。
1. 拷贝主题下的`gulpfile.js` `travis.yml` `travis.sh` 到项目根目录

2. 配置travis.yml 文件
``` yml
language: node_js #使用Node语言环境
node_js: stable #安装稳定版Node

sudo: false

#cache 启用缓存，加快构建速度
cache:
  directories:
    - "node_modules"

notifications: #启用通知
  email:
    recipients:
      - snippet@91h5.cc #接收构建消息的邮件 不需要可设置为false
    on_success: never #部署成功时，可设置alway never change
    on_failure: always #部署失败时，同上

# S: Build Lifecycle

before_install:
  - sudo apt-get install libnotify-bin #支持linux桌面提醒库

install:
  - npm install  #安装依赖

before_script:
  - export TZ='Asia/Shanghai' #设置时区
  - npm install -g gulp  #全局安装Gulp
  - chmod +x _travis.sh  #授权脚本执行权限

script:
  - hexo clean && hexo g #清除缓存并生成静态文件
  - gulp #执行gulp任务

after_success: #执行成功时(以后扩展功能使用)

after_script:
  - ./_travis.sh #执行部署脚本
# E: Build LifeCycle

branches:
  only:
    - dev #需要监听部署的分支
env:
  global:
   - GH_REF: github.com/shenliyang/shenliyang.github.io.git #更改为自己git地址
```

3. Submit code to Github for automatic deployment
4. When the `.travis.yml` configuration file has been modified, submit it to the hexo branch of the remote repository. At this point, if everything is ok in the previous configuration, we should be able to see on the home page of the Travis CI blog project that the automatic build has been completed. The above will display the log information and status during the build process.

## 3. Theme development
Gulp implementation enables theme development mode
``` bash
gulp dev
```
Will listen for changes in styleless or JS files. Then execute [Topic Release] above.

### Run preview
``` bash
hexo clean && hexo g && hexo s -p 4000
```

Use your browser to open the address `http: // localhost: 4000` for preview.

# **Others**

## Thank you
In designing this theme, I have referred to the design and creativity of many themes and blogs, thank you very much!

## Encourage
**If you think this theme is good, your support and encouragement is the biggest motivation for subsequent updates.**

## Aim
**Dedicated to the simple and lightweight theme, easy to configure out of the box**, this theme project will be continuously maintained and updated, will not run away, please use it with confidence.

## Contribution
Accept all forms of contribution, including but not limited to submitting issues or needs, fixing code.
Everyone is welcome to mention Issue or Pull Request.

> The Hexo framework is fast, simple and efficient. Friends who like to be gorgeous, add various functions, and toss, I suggest you move to [wordpress] (https://wordpress.org/)


## Common Problem

#### 1. The search function is unavailable, and the content.json file cannot be found?

Need to install the **hexo-generator-json-content** plugin:

``` bash
npm i hexo-generator-json-content@2.2.0 -S
```

#### 2. Google search is not working?

If using Google search does not respond, determine if you are online.

#### 3. How to set the thumbnail of the homepage article to automatically retrieve the images in the article?

**Homepage article thumbnail loading rules :** custom article thumbnails > automatic retrieval of images in articles > defaultImgs (randomly acquired) > list without image mode

In `Front-matter`:
Specify img variable-> fixed thumbnail
Do not specify the img variable-> automatically retrieve images in articles


#### 4. Where can I access local static files at url?

Create a new folder under the theme `source` directory, for example:` static` folder, and then add static resources, for example: xxx.pdf file, visit: * `http: //yoursite.com/static/xxx.pdf`*

#### 5. Does this theme have pagination?

Theme has integrated paging function, can be modified in Hexo configuration

| Parameter       | Description        | Defaults  |
| ------------- |:-------------:| :-----:|
| per_page     | Number of articles displayed per page (0 = pagination off) |  10 |
| pagination_dir     | Paging Directory      |   page |


#### 6. Disagreements on Hexo tags and classification methods

> Only articles support classification and tags, you can set them in Front-matter. In other systems, classifications and labels sound similar, but there are obvious differences between the two in Hexo: classifications are sequential and hierarchical, that is, `Foo, Bar` is not equal to` Bar, Foo`; and tags There is no order or hierarchy.

If you have any experience using WordPress, it is easy to misunderstand how Hexo is classified. WordPress supports multiple categories for an article, and these categories can be siblings, or parent-child categories. But Hexo does not support specifying multiple peer classifications. The following methods are specified:

``` bash
categories:
- Diary
- Life
```

Makes the classification Life a sub-category of Diary, rather than a side-by-side classification. Therefore, it is necessary to choose the classification that is as accurate as possible for your article.

Hexo official documentation: [Categories & Tags](https://hexo.io/docs/front-matter#Categories-amp-Tags)

#### 7. The tags and categories pages are displayed incorrectly and cannot be accessed, showing 404?

When using topic access, domain name + / tags or domain name / / categories is normal if you access 404. Because these paths are not part of the theme or Hexo framework. Instead, the user actively creates new pages and extends them.

You can create new pages, such as tags and categories, in the following command format:

```bash 
 hexo new page tags 和 hexo new page categories
````

> Did not find the solution to the problem you need, I suggest reading "Issues Tips You Didn't Know" and mentioning Issues.

## Version update log

  - Added Gitalk review system
  - Add blog automation deployment results to mobile phone nails in real time, and learn the deployment situation the first time

  Example of automated deployment result notification:

  ![Example of automated deployment result notification](https://s2.ax1x.com/2019/03/06/kvnejs.jpg)

## License

[MIT License](/LICENSE)
