# 背景
想搭建一个自己的博客站点，正在调研Gitbook。


# 环境
MacBook Pro 2021
芯片：Apple M1 Pro
MacOS：14.6.1 (23G93)
Nebula官网：https://www.nebula-graph.com.cn/
Nebula网页体验版：https://explorer.nebula-graph.com.cn/explorer


# 配置流程
Gitbook安装

1、安装node.js

Gitbook不支持高版本的node.js，建议使用v10.16.0 版本的node.js；
这里是一个大坑，版本问题非常严重；不按照这里的操作来，会导致gitbook安装不成功
https://nodejs.org/zh-cn/download/prebuilt-installer
Node.js v10.24.1
npm v6.14.12


https://xiaochaowei.com/2020/01/10/InstallGitBookOnMAC/
mac下安装gitbook


文档
https://docs.gitbook.com/content-editor/editor

github绑定gitbook并互相同步
https://blog.csdn.net/young2415/article/details/112427188


gitbook不能在线编辑！！


node.js 卸载
sudo rm -rf /usr/local/lib/node_modules /usr/local/lib/node
sudo rm -rf /usr/local/lib/node /usr/local/lib/node_modules /var/db/receipts/org.nodejs.*
sudo rm -rf /usr/local/include/node /Users/$USER/.npm
sudo rm /usr/local/bin/node
sudo rm /usr/local/share/man/man1/node.1
sudo rm /usr/local/lib/dtrace/node.d


使用方法：
在本地用vscode编辑
然后commit到github
然后从github同步到gitbook

还可以用Gitbook-Ext 修改Gitbook模板这些插件来维护gitbook电子书的版式
当然平台本身提供了无版式、简单版式两种情况


关于实时编辑，有这样的解释
https://docs.gitbook.com/content-editor/editor/live-edits
