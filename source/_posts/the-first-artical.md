---
title:  Hexo+Github/Coding 搭建自己的博客
date: 2017-11-21 10:53:49
tags: 技术
---


## 为什么要自己搭建博客

> 现在网上一大堆写博客的地方，就是想弄个自己的博客，逼格高点吧，想改成什么样就改成什么样，当然，主要还是记录生活、工作等等方面自己想记录的东西，这篇文章也是为了总结自己搭建博客的过程，也希望能给那些想自己玩博客的人提供一点帮助吧。我的博客及写文章就从这篇文章开始吧。

## 开始之前的介绍
gitHub是一个面向开源及私有软件项目的托管平台，极大推进软件行业的进步，想必大家应该都知道gitGub，详细介绍就自行百度吧。
coding也是一个代码托管平台，说实话之前我不知道coding（尴尬），开始搭建博客才知道有coding，在国内coding要比github快，服务器部署在中国嘛。
Hexo 是基于node.js 生成静态网页的工具。

总体思路就是通过hexo生成静态页面，部署到github和coding上。接下来就开始干吧

##   环境搭建 
### git安装 
  
-  根据自己的电脑系统下载Git Bash对应的安装文件
	  [下载地址](https://git-for-windows.github.io/) : 安装一路next

 ![这里写图片描述](http://img.blog.csdn.net/20171123143621358?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast) 
 
-  安装好后打开Git Bash检查git版本 命令：git version
 
 ![这里写图片描述](http://img.blog.csdn.net/20171123143949391?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
### Node.js的安装 
-   根据自己的电脑系统下载Node.js对应的安装文件：

 [下载地址](https://nodejs.org/en/download/) : 安装一路next
![一直next](http://img.blog.csdn.net/20171123112844980?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
		
- 安装好后打开Git Bash检查node.js版本 命令：node -v

 ![这里写图片描述](http://img.blog.csdn.net/20171123144707312?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

### 安装hexo
- 先创建一个文件夹blog，用来存放日志，进到blog文件夹 右键 选择Git Base
- 安装hexo命令：npm i -g hexo
- 安装完毕 检查hexo版本 命令 hexo -v
![这里写图片描述](http://img.blog.csdn.net/20171123151537706?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

- 初始化hexo命令：hexo init
blog 文件夹下目录结构发生变化
![这里写图片描述](http://img.blog.csdn.net/20171123151938254?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

 node_modules：是依赖包
 public：存放的是生成的页面
 scaffolds：命令生成文章等的模板
 source：用命令创建的各种文章
 themes：主题
 _config.yml：整个博客的配置
 db.json：source解析所得到的
 package.json：项目所需模块项目的配置信息

### 感受一下hexo
- 忙了半天，也没看到效果，好吧，现在就要看一下效果，感受一下hexo
- 同样在命令行中输入：hexo g  意思是编译成静态页面，因为我里面的内容比较多 可能会和你有点出入，没关系
 ![这里写图片描述](http://img.blog.csdn.net/20171123153742697?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

- 然后输入：hexo s  启动本地项目
 ![这里写图片描述](http://img.blog.csdn.net/20171123154322521?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

- 在浏览器中打开http://localhost:4000/，你将会看到：
![这里写图片描述](http://img.blog.csdn.net/20171123154619743?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

 hexo 可以正常工作了 
## hexo连接到github和coding
- 首先要有个github账号，没有的话，就去注册一个，有账号就直接new repository 仓库名称： yourname.github.io （yourname 是你的github账号）
，你可能会想为什么要这么命名仓库名称，因为只有这样，你部署到github之后 才能用yourname.github.io 访问，不用输入项目名称，爱玩的可以试一下别的仓库名字 。
![这里写图片描述](http://img.blog.csdn.net/20171123153147695?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

- 仓库建好之后，回到git bash 窗口，配置github用户户信息
(yourname : 你的账号名称，yoursemail: 你github绑定的邮箱) 
git config --global user.name "yourname"
git config --global user.email "yoursemail@163.com"

- 生成密钥 （注意C大写）
ssh-keygen -t rsa -C "yoursemail@163.com"
生成之后通过以下方法找到生成好的秘钥
cd ~/.ss
cat id_rsa.pub
![这里写图片描述](http://img.blog.csdn.net/20171123160112955?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
- 将获取的秘钥放到github
![这里写图片描述](http://img.blog.csdn.net/20171123160623715?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
![这里写图片描述](http://img.blog.csdn.net/20171123160642448?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

- 在gitbash中验证是否添加成功：ssh -T git@github.com

 ![这里写图片描述](http://img.blog.csdn.net/20171123161040975?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

- 配置_config.yml文件
在blog文件夹下找到_config.yml文件，文件最下面找到Deployment，然后按照如下修改： （注意 ：冒号之后都是有一个半角空格的）

 deploy:
  type: git
  repo: git@github.com:yourname/yourname.github.io.git，master
- 上传到github
先安装一波：npm install hexo-deployer-git --save 
执行命令(建议每次都按照如下步骤部署)：

 hexo clean  // 清楚缓存
hexo g  // 编译文件
hexo d // 部署文件

 浏览器中输入地址 http://yourname.github.io 你就会看到你的博客了， 有没有很兴奋 。

## 逼格升级（绑定你自己的域名）
- 如果没有域名就算了，如果你有空闲的域名可以绑定到自己的博客
- 添加俩记录 如果没有 就点击右上角 快速设置解析模仿着我的添加就行
- 注意：记录值填写 yourgitname.github.io,俩都填这个，我看到有别的文章让填ip的，但是ip有时候会变 ，我建议填写yourgitname.github.io,  yourgitnae:是你自己的github账号 切记

![这里写图片描述](http://img.blog.csdn.net/20171123164749967?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

- github仓库设置一下 
![这里写图片描述](http://img.blog.csdn.net/20171123165720507?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

往下来
![这里写图片描述](http://img.blog.csdn.net/20171123165828844?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvcXFfMjE5ODQyODc=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

- 十分钟之后，浏览器输入你的域名 就能访问你的博客了。

## 结束语
coding，留言板 后续补上，
就写到这吧，写一天了，第一次写文章，感觉好累，给那些经常写文章的人说句“辛苦了”。如果在搭建的时候 你们出现什么问题 ，请在下面留言，我会尽快给与回复，如果哪写错了  也可以在下面留言指出来，感激不尽。

转载请注明原博客地址： [Hexo+Github/Coding 搭建自己的博客](http://mliuheng.com/2017/11/21/the-first-artical/) 
