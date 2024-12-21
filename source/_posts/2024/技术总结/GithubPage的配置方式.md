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

网上的教程这个很全：
https://pages.github.com/
https://blog.csdn.net/yaorongke/article/details/119089190


# 环境
以下两种环境都可以成功安装，已实测过。

## Mac
MacBook Pro 2021  
芯片：Apple M1 Pro  
MacOS：14.6.1 (23G93)  
node版本：v16.20.2  
npm版本：8.19.4  

## Windows
Windows 11 专业版  
芯片：13th Gen Intel(R) Core(TM) i7-13700   2.10 GHz  
node版本：v16.20.2  
npm版本：8.19.4  


# 配置流程

## 第一步、安装node.js
在node官网选择版本安装即可，这这一步很简单  
https://nodejs.cn/en/download

## 第二步、创建仓库
仓库名称的格式一定要为${name}.github.io这种格式，例如rabbit710.github.io

仓库目前只支持public

## 第三步、打开原生博客
在浏览器输入https://${name}.github.io网址，就可以打开博客站点了，非常简单

## 第四步、安装hexo
原始的博客模样过于简单，可以使用别人开发好的博客框架，我们在框架里面写文章即可。

博客框架：https://hexo.io/zh-cn/

本质上它就是一个前端UI的脚手架，选一个自己喜欢的样式，然后就可以按照它的用法去写文章，不用管css等前端配置了。

hexo还有很多主题可以选择（其实就是hexo的皮肤），我选择的主题是Fluid，具体配置方法可以参考：https://github.com/fluid-dev/hexo-theme-fluid


```shell
npm install -g hexo-cli  # 安装hexo
npm install --save hexo-theme-fluid  # 安装hexo-fluid模板
hexo server  # 启动博客，即可在浏览器打开
```

## 第五步、写文章
在本地文件目录的 _posts 文件夹下面写文章，按照hexo的格式来、然后结合自己的喜好做一些微调即可。

## 第六步、提交代码
将内容commit到github


# 问题

## Windows安装node之后，关闭cmd窗口，输入`node -v`失效
问题在于Windows没有自动创建环境变量，要把node的安装路径加到环境变量里面。

安装路径类似：C:\Users\admin\AppData\Roaming\fnm\node-versions\v16.20.2


## Windows启动`hexo server`失败

通过npm安装好hexo之后，输入`hexo server`启动报错，如下图所示

<img src="https://githubpage-1304373050.cos.ap-guangzhou.myqcloud.com/20240920-githubpage-01.png?q-sign-algorithm=sha1&q-ak=AKIDiIS4FnWA6THWAZCFWxpn86XUO7H4GR8G89iaAmain3_2He0SO4GdWzx0RN4Nq1Cx&q-sign-time=1734763140;1734766740&q-key-time=1734763140;1734766740&q-header-list=host&q-url-param-list=ci-process&q-signature=90e753d6174cfa777d0488f7d26b7502a9982b94&x-cos-security-token=Ru5RBfbPLr9I79dfxau61fHubtO0fv9a33d29a7ed38bfa3d96b02940ec4e358e40dMl5_kcVgoI37hZwbYdK8Gf_yapUnXeNZ7nxezRWGTerCLvFHOSI4PbE75m1kHa7c7Jd3EaoF7Ox6oFvsj00p8BFN6CAzL99EklbufvQOWr4sIggdxDrA6O9ommQbc40IaTTO2Q1aJQI72NAhXQnb9akpWgTxKwjWpEeL7xKn5esd-6izh0tb15hVbVErs&ci-process=originImage" width="100%" height="100%" title="报错" alt="报错"/>

解决办法是调整windows11中的开发者选项，如下图所示

<img src="https://githubpage-1304373050.cos.ap-guangzhou.myqcloud.com/20240920-githubpage-02.png?q-sign-algorithm=sha1&q-ak=AKIDesYqAomBdQ-Q_tofWVSQhvyDwGBg2HRksyaxFF5dvRXo4NFPqnTbHCpf5e7JpTQ_&q-sign-time=1734763178;1734766778&q-key-time=1734763178;1734766778&q-header-list=host&q-url-param-list=ci-process&q-signature=4650e722bb01795740c9e04b793d86b39df5c6dc&x-cos-security-token=1c2o3Qqx32P72eZRGBgxNjVfcDCUYAQa6793e3c3174b72987594a959257d8476DJDECAQ3F7dLC5YBAykLYXF0DramgMMeXM4AWP6-bk-oPwkoQHaq-0Ee8LHEDxGbgelzOcefHjMxrVVlT7wblkPsrhxvvIQkvffXI_Ei9UM9GKW-nsAA2ZLljJZvFs0kTqMTBfF6nCBWEkqUw5fzGURvnTvzkIcz7pG-f0OR9E_rpAq91G-PUzEClummplml&ci-process=originImage" width="100%" height="100%" title="报错" alt="报错"/>

