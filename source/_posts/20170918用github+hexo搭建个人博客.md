---
title: 用github+hexo搭建个人博客
date: 2017-09-18 21:35:59
tags: hexo
---

## 前言

上完新生大学的javascript课程，了解github的基本用法，发现编程世界精彩无比。鉴于大家的推荐及建议，准备利用hexo搭建个人博客，操作步骤如下：

1. 安装git客户端
2. 安装node.js
3. 安装hexo
4. 生成静态网页
5. 创建github仓库
6. 上传至github

<!--more-->

## 1、安装git客户端

- 我的是windows操作系统，用的是 Git SCM, https://git-scm.com/download/win

## 2、安装node.js

- 安装nvm（nvm的全称是：Node Version Manager，就是用于管理node.js的版本的工具），官网下载链接：[nvm-windows Releases](https://github.com/coreybutler/nvm-windows/releases)，配置好环境变量。

  鉴于国内有些地方无法下载npm及node.js，最好配置下镜像地址，在安装目录下的`settings.txt`后面加两行：

  ```
  node_mirror: https://npm.taobao.org/mirrors/node/
  npm_mirror: https://npm.taobao.org/mirrors/npm/
  ```

- 然后安装node和npm：按下快捷键`Win+R`，在弹出的`运行`对话框中，输入`cmd`，打开命令行窗口，输入`nvm install 8.0.0`，默认是64位的，如果是32位的则要输入`nvm install 8.0.0 32`。

## 3、安装hexo

- 先创建个空文件夹，然后cd到目录下，输入命令`npm install hexo-cli -g`。
- 接着初始化`hexo init`,产生以下文件；

![hexo-init](https://github.com/yousl/yousl.github.io/wiki/hexo-init.png)

## 4、生产静态网页

- 输入命令`hexo generate或g`，然后`hexo server或s`，就可以在本地浏览器中输入`localhost:4000`来看到自己的博客网页。



**以下是介绍如何把博客部署到github上的 **

---

##  5、创建github仓库

- 先注册账户，并新建一个repo，名称为`yourname.github.io`, 注意`yourname`是你的github名称。

## 6、上传至github

- 先安deployer插件：`npm install hexo-deployer-git --save`

- 用编辑器打开`_config.yml`，修改deplay的配置如下(冒号之后都是有一个半角空格的)：

  ```
  deploy:
    type: git
    repo: https://github.com/YourgithubName/YourgithubName.github.io.git
    branch: master
  ```

- cd到你的博客目录下，分别执行以下命令：

  ```
  hexo clean
  hexo generate或g
  hexo deploy或d
  ```

- 然后在github上你的repo的settings中设置GitHub Pages，启用Source为你的master branch。

  ![githubpages](https://github.com/yousl/yousl.github.io/wiki/githubpages.png)

- 在浏览器中输入`http://yourgithubname.github.io`就能看到你的博客主页了。

  ​