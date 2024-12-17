---
title: GithubPage的配置方式
subtitle: GithubPage的配置方式
date: 2024-09-20
categories: 技术总结
tags: 
---


# 背景
想搭建一个自己的博客站点，采用github.io + 静态站点的方式部署。
github.io是github里面一种特殊的代码仓库模板，给用户专门搭建博客用的。比起在csdn、知乎写博客，github.io的优点在于，没有过多的内容审查限制、原始文档在本地也可以保存。

网上的教程这个很全：https://blog.csdn.net/yaorongke/article/details/119089190


# 环境
MacBook Pro 2021
芯片：Apple M1 Pro
MacOS：14.6.1 (23G93)
npm版本：8.19.4
node版本：v16.20.2
https://github.com/rabbit710/rabbit710.github.io?tab=readme-ov-file


# 配置流程

## 第一步、创建仓库
仓库名称的格式一定要为${name}.github.io这种格式，例如rabbit710.github.io
仓库目前只支持public

## 第二步、打开原生博客
在浏览器输入https://${name}.github.io网址，就可以打开博客站点了，非常简单

## 第三步、选择博客样式
原始的博客模样过于简单，可以使用别人开发好的博客框架，我们在框架里面写文章即可。
博客框架：https://hexo.io/zh-cn/
hexo还有很多主题可以选择（其实就是hexo的皮肤），我选择的主题是Fluid，具体配置方法可以参考：https://github.com/fluid-dev/hexo-theme-fluid

## 第四步、写文章
在本地文件目录的 _posts 文件夹下面写文章，按照hexo的格式来、然后结合自己的喜好做一些微调即可

## 第五步、本地测试
cd进入项目根目录，然后输入`hexo server`命令，就会在本地启动这个node.js服务
然后在本地进行调试；觉得ok之后就可以commit到github了
