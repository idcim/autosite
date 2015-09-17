## Ghost 7.0 正式发布

![](http://static.ghostchina.com/image/2/50/0a96874d2150820509ec84099a154.png)

[Ghost 0.7.0](http://www.ghostchina.com/download/) 已经正式发布了！此版本主要对后台 UI 的重构，既包含重新设计，也包含底层功能的重大改进。0.7.0 还为即将到来的 API 做了很多铺垫工作。

Ghost 0.7.0 的主要改进

* **[新增]** 设计新后台界面

* **[新增]** 后台能够搜索博文和用户

* **[新增]** 安装流程（针对新博客）

* **[改进]** jQuery 不再包含在 {{ghost_foot}} 输出中

* **[改进]** 保存标签的添加顺序

* **[改进]** `{{foreach}}` 助手函数

* **[修复]** `{{tags}}` 和 `{{author}}` 不出现在用于获取前一篇/后一篇博文的助手函数中

* **[修复]** 多个涉及 RSS 链接的问题

* **[修复]** 非常早版本的升级路径

可以在这里查看[完整的升级日志](https://gist.github.com/ErisDS/314914b570c4233eea8c)。

下载地址

http://www.ghostchina.com/download/

强烈建议大家下载并使用 Ghost 0.7.0 中文版完整集成包，以免 `npm install --production` 安装依赖包时被墙！

---


## Ghost 7.0 中文集成版 Dockerfile


这个仓库包含[Ghost v7.0 中文集成版本](http://www.ghostchina.com/) 的[Docker](https://www.docker.com/)自动创建 [automated build](https://registry.hub.docker.com/u/dockerfile/ghost/) Ghost镜像到 [Docker Hub Registry](https://registry.hub.docker.com/)公有库的 **Dockerfile** .


### 基础docker镜像

* [dockerfile/nodejs](http://dockerfile.github.io/#/nodejs)


### 安装

1. 安装 [Docker](https://www.docker.com/).

2. 下载 [自动创建的Ghost镜像](https://registry.hub.docker.com/u/dockerfile/ghost/) 从 [Docker Hub Registry](https://registry.hub.docker.com/): `docker pull dockerfile/ghost`

   (或者你可以从 Dockerfile 创建: `docker build -t="dockerfile/ghost" github.com/dockerfile/ghost`)


### 使用

    docker run -d -p 80:2368 dockerfile/ghost

#### 定制 Ghost

    docker run -d -p 80:2368 -v <override-dir>:/ghost-override dockerfile/ghost

`<override-dir>` 可以包含绝对路径的目录:

*  `config.js`: 从 [这里](https://github.com/TryGhost/Ghost/blob/master/config.example.js)复制自定义配置文件 (必须更改 `127.0.0.1` 为 `0.0.0.0`)

* `content/data/`: 持续/共享的数据

* `content/images/`: 持续/共享的图像

* `content/themes/`: 更多主题

等待几秒钟后, 在浏览器中打开 `http://<host>` 博客或者 `http://<host>/ghost` 博客后台。

## 代码创建和维护

* QQ: 479608797

* 邮件:  fenyunxx@163.com

* [github](https://github.com/xiongjungit/docker-ghost)

* [dockerhub](https://hub.docker.com/r/dockerxman/)
