+++
date = '2025-10-31T15:51:24+08:00'
draft = false
title = 'Hugo静态博客-快速入门指南'
+++
# Hugo 快速入门指南

![Hugo Logo](http://gohugo.io/images/hugo-logo-wide.svg)

## 简介
Hugo 是一个流行的静态网站生成器，能够帮助用户快速创建高性能的网站。本文将引导你在几分钟内搭建一个 Hugo 网站。

## 目录
- 前提条件
- 创建站点
  - 命令行操作
  - 命令详解
- 添加内容
- 配置站点
- 发布站点
- 求助与资源

---

## 前提条件
在开始之前，请确保你已经：

1. 安装了 Hugo（扩展版或扩展部署版，版本要求 v0.128.0 及以上）。详细安装教程见：[Hugo 安装指南](http://gohugo.io/installation/)
2. 安装了 Git，安装教程见：[Git 安装指南](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
3. 熟悉命令行操作。

> **注意（Windows 用户）**：
>- 请避免使用命令提示符（Command Prompt）和 Windows PowerShell。
>- 推荐使用 PowerShell（最新版）或 Linux 终端（如 WSL 或 Git Bash）。

## 创建站点

### 主要命令
```bash
hugo new site quickstart
cd quickstart
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
echo "theme = 'ananke'" >> hugo.toml
hugo server
```

执行以上命令后，你可以在终端显示的地址访问你的网站。

### 命令详解
- `hugo new site quickstart`：创建名为 `quickstart` 的项目目录及基本目录结构。
- `cd quickstart`：进入项目根目录。
- `git init`：初始化一个空的 Git 仓库。
- `git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke`：将 Ananke 主题作为子模块添加到项目中。
- `echo "theme = 'ananke'" >> hugo.toml`：在配置文件中指定主题。
- `hugo server`：启动 Hugo 开发服务器，实时预览网站。

> 按 `Ctrl + C` 停止开发服务器。

## 添加内容

创建新内容页面：
```bash
hugo new content/posts/my-first-post.md
```
此命令会在 `content/posts` 文件夹下生成一个 Markdown 文件，默认带有如下 Front Matter：
```toml
+++
title = "My First Post"
date = 2024-01-14T07:07:07+01:00
draft = true
+++
```

- `draft = true` 表示该内容为草稿，默认不会被发布。
- 你可以编辑正文部分，使用 Markdown 语法，例如：

```markdown
## 介绍

这是**加粗**文本，和*斜体*文本。

访问 [Hugo 官网](https://gohugo.io)
```

启动开发服务器时，使用 `--buildDrafts` 或 `-D` 参数可以包含草稿内容：
```bash
hugo server --buildDrafts
# 或
hugo server -D
```

编辑完成并准备发布时，请将 `draft` 设置为 `false`。

Hugo 支持 CommonMark 标准的 Markdown，官方提供了[在线测试工具](https://spec.commonmark.org/dingus/)。

## 配置站点

在项目根目录打开 `hugo.toml` 配置文件，示例如下：

```toml
baseURL = 'https://example.org/'
languageCode = 'en-us'
title = 'My New Hugo Site'
theme = 'ananke'
```

需要根据实际情况修改：
1. `baseURL`：生产环境下网站的基础 URL，需以协议开头并以斜杠结尾。
2. `languageCode`：语言和地区代码，如 `zh-cn`。
3. `title`：网站标题。

保存后重新启动服务器查看效果：

```bash
hugo server -D
```

不同主题可能有额外的配置项，建议查看主题的官方文档。例如，Ananke 主题的配置和使用指南见其[GitHub 仓库](https://github.com/theNewDynamic/gohugo-theme-ananke#readme)和[演示站点](https://gohugo-ananke-theme-demo.netlify.app/)。

## 发布站点

执行以下命令生成完整的静态网站文件：

```bash
hugo
```

生成的文件位于 `public` 文件夹内，包含 HTML、图片、CSS 和 JavaScript 等资源。

> 注意：默认不包含草稿、未来或过期内容。

部署网站到服务器或托管平台请参考 Hugo 的[托管与部署指南](http://gohugo.io/host-and-deploy/)。

## 求助与资源

- Hugo 官方论坛：[https://discourse.gohugo.io/](https://discourse.gohugo.io/)，社区活跃，适合提问和查找问题答案。
- 阅读求助指南：[请求帮助注意事项](https://discourse.gohugo.io/t/requesting-help/9132)
- 更多学习资源，包括书籍和视频教程，见：[外部学习资源](http://gohugo.io/getting-started/external-learning-resources/)

---

## 相关链接
- [Hugo 官网](http://gohugo.io/)
- [Hugo 文档](http://gohugo.io/documentation/)
- [Hugo 主题库](https://themes.gohugo.io/)
- [Hugo GitHub 仓库](https://github.com/gohugoio/hugo)

---

![](http://gohugo.io/images/qr/qr_c8e55b47edb2407c.png)

扫码访问 Hugo 快速入门页面
