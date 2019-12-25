---
title: How to config a blog site
date: 2019-07-14 18:38:45
tags:
    - 玩耍
    - BeYourself
mp3: /statics/madirection.mp3
cover: /img/sby.jpeg
---

## 使用-Hexo-搭建自己的个人静态博客

**Hello every one!**

## 环境

必须安装 Node 环境
通过在终端任意目录输入 ① `node -v` 查看是否有输入node的版本

## 安装hexo 本地运行

*Hexo 是一个命令行应用程序*

在终端的任意目录输入 ② `npm install -g hexo-cli` 然后回车执行等待安装成功
通过输入 ③ `hexo –version` 如果看到输入一大堆的版本号就说明安装成功了，接下来就可以创建博客目录了
接下来在桌面目录下通过输入 ④ `hexo init 博客项目存储目录`
Hexo 会在你执行该命令的目录下生成一个博客项目

*初始化博客项目的过程需要联网*

接下来通过终端`进入刚才创建的博客项目目录`，然后在该目录下输入 ⑤ `npm install` 回车等待执行结束
接下来输入 ⑥ `hexo server` 回车执行，它会在你的本地启动一个服务器，然后就可以访问你的博客项目
这时候在浏览器中输入 localhost:4000 就可以在本地访问到你的博客啦。

## 配置hexo界面

找到_config.yml，设置里面的参数(一般跟作者，主题等相关)，之后需要 `hexo server` 重启本地服务器
在 hexo 官网找到主题页面，找到你喜欢的主题，去github上把该主题项目下下来
进入到你的博客项目地址下的themes中 `git clone 主题地址 –depth 1` 把该主题最新版文件下下来
然后在_config.yml配置文件中 `theme:主题文件夹名` 引用，

## 在hexo中加入自己的博客文章

进入博客项目，输入 ⑦ `hexo new 文章名称` 创建博客
该命令会自动在 source/_posts/ 目录下生成一个 文章名称.md 文件（就在这里面写你的文章）

## 生成html文件

生成静态文件：⑧ `hexo generate`
>该命令会自动在项目的根目录下的 public 目录下降静态文件放进去吧,每次写了新的文章都要执行一次

*****

**到了激动人心的时刻啦！！!**

## 快速部署到以github-io为后缀的域名中 

### 修改配置文件 在下载下来的博客项目中（自己本地的）找到 _config.yml 找到

deploy: （注意键值对中间是空格 也就是type：空格git..）
type: git
repo: [https://Cassieqian:123456@github.com/Cassieqian/Cassieqian.github.io.git](https://Cassieqian:123456@github.com/Cassieqian/Cassieqian.github.io.git)
这里的地址是github用户名：用户密码@创建的可以直接访问域名的仓库地址

在项目根路径下执行 ⑨ `npm install hexo-deployer-git –save` 该命令
接下来就可以直接输入 ⑩ `hexo deploy –generate` 自动发布到 github 上
在浏览器中输入 github 用户名.github.io 就可以访问你的博客了

 #### 注意事项

有新文章加入，再次发布的时候 ⑦ ⑧ ⑩
