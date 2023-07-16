---
title: My Site GitHub Pages Starter
date: 2023-07-16 18:21:46
tags: Hexo
categories: Hexo
---

# GitHub Page Starter

## 1. Github Pages

References：[GitHub Pages | Websites for you and your projects, hosted directly from your GitHub repository. Just edit, push, and your changes are live.](https://pages.github.com/)



## 2. Hexo Blogs

References:   

1. [GitHub+Hexo 搭建个人网站详细教程 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/26625249)

2. [Hexo](https://hexo.io/zh-cn/)

首先创建一个基于Hexo-markdown的my-blogs博客项目，注意这个并不是github.io.仓库。

Note: 注意这里也可以下载由KeepTheme提供的模板工程代替my-blogs项目：[Keep 主题快速启动模板 | Keep 主题使用指南 (xpoet.cn)](https://keep-docs.xpoet.cn/tutorial/get-start/quick-starter.html)

```shell
npm install hexo-cli -g
hexo init my-blogs
cd my-blogs
npm install
hexo server


# 建议采用下载模板的方式
mv hexo-theme-keep-starter-main my-blogs
cd my-blogs
git init
git branch -M main
npm install
```

## 3. Hexo theme

> Reference
>
> 1. [Themes | Hexo](https://hexo.io/themes/)
>
> 2. [Keep 主题使用指南 | Hexo 主题 Keep 官方文档 (xpoet.cn)](https://keep-docs.xpoet.cn/)

## 4. manually push to GitHub io pages

GitHub: create empty repository  username.github.io

Install plugin `hexo-deployer-git`

```
npm install hexo-deployer-git --save
```

找到`_config.yml`文件，找到`deploy`，按照以下格式进行修改：

```shell
# 注意先给Github配置本机的ssh-key 才能部署到Github
deploy:
  type: git
  repo: https://github.com:你的用户名/你的用户名.github.io.git
  branch: main
```

手动构建项目生成静态页面和部署到GitHub

```
hexo clean  # 清除缓存
hexo g      # 生成静态网页
hexo d      # 部署到Github
```

## 5. Suggest Auto push to GitHub pages by GitHub Actions

使用这个代替上面的手动发布，私有源码库创建到my-blogs，公开库创建到username.github.io。

参照下面的链接文档

> [如何使用 GitHub Actions 自动部署 Hexo 博客 - 掘金 (juejin.cn)](https://juejin.cn/post/6943895271751286821)

## 6.create a menu page

update keep.yml

```
menu:
  Home: /
  Archives: /archives
  Tags: /tags
  Categories: /categories
  # Links: /links
  About: /about
  # Changelog: /changelog
  # ......
```

create menu about page and edit about

```
hexo new page about

```

create new page
```
hexo new my-site-starter
```

