# 背景
Nebula是一款国人开发的图数据库，简单好用、试用免费、中文社区活跃，因此我选择nebula来对数据血缘关系做可视化。

以下记录在本机配置nebula的过程。


# 环境
MacBook Pro 2021
芯片：Apple M1 Pro
MacOS：14.6.1 (23G93)
Nebula官网：https://www.nebula-graph.com.cn/
Nebula网页体验版：https://explorer.nebula-graph.com.cn/explorer


# 配置流程


## 第一步、安装引擎
最方便的方式是基于Docker.app在本地部署，但由于Docker.app在商业领域有法务风险，因此无法复现这个流程了。因此，我们只能选择Docker Compose的方式安装。

参考教程是：https://docs.nebula-graph.com.cn/3.5.0/2.quick-start/1.quick-start-overview/

另外，建议不要在Windows系统安装，在Wondows上使用Docker会很麻烦。一般推荐Mac或者Linux。


## 第二步、安装图形化界面Studio



# 报错及处理

## 使用`docker-compose up -d`第一次启动容器时报错

报错日志为
`Error response from daemon: Head "https://registry-1.docker.io/v2/vesoft/nebula-console/manifests/v3.5": Get "https://auth.docker.io/token?account=mesong&scope=repository%3Avesoft%2Fnebula-console%3Apull&service=registry.docker.io": tls: failed to verify certificate: x509: certificate is valid for *.atlassolutions.com, *.atdmt.com, *.atdmt2.com, *.atlassbx.com, *.xx.atlassbx.com, atdmt.com, atdmt2.com, atlassbx.com, atlassolutions.com, xx.atlassbx.com, not auth.docker.io`

本质原因是网络连接不是，docker官方在202408把中国列为禁用地区，因此国内是连接不到docker官方的软件源的。参考这个文档切换可用的docker源 `https://github.com/DaoCloud/public-image-mirror/issues/2328`


