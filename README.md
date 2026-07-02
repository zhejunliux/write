# write — 4587.fun 写作站

[https://write.4587.fun](https://write.4587.fun) 的博客，基于 [Hugo](https://gohugo.io) + hugo-bearcub 主题。
从原 GitLab 站迁移而来。push 到 `main` 后 GitHub Actions 自动构建部署。

## 写一篇新文章

在 `content/write/<分类>/` 下新建一个 `.md` 文件（GitHub 网页：进目录 → Add file → Create new file）。

现有分类：`live`（生活）、`film`（电影）、`music`（音乐）、`technology`（技术）。想加新分类，直接建新子目录即可。

文件开头**必须**有 front matter（两行 `---` 之间的元信息）：

```markdown
---
title: "文章标题"
date: 2026-07-02
description: "一句话简介"
tags: ["live"]
categories: ["live"]
---

正文从这里开始，用 Markdown 写。
```

- `title` 标题、`date` 日期（`YYYY-MM-DD`）、`tags`/`categories` 分类标签
- 文件名（如 `my-post.md`）会成为网址的一部分：`write.4587.fun/write/<分类>/my-post/`
- 建议英文文件名（中文也可，但网址会被编码得很长）

Commit 后几十秒自动发布。

## 插入图片 / 音频 / 视频

1. 把媒体文件传到对应目录：图片 → `static/images/`，音频 → `static/audios/`，视频 → `static/vedios/`
2. 在文章 Markdown 里用 HTML 标签引用（路径以 `/` 开头，指向 static 根）：

```html
<img src="/images/我的图.jpg">
<audio controls><source src="/audios/我的歌.mp3" type="audio/mpeg"></audio>
<video controls width="320" src="/vedios/我的视频.mp4"></video>
```

（本站配置允许在 Markdown 里直接写 HTML，所以媒体标签原样生效。）

## 主页 / 导航 / 友链

- **首页**那段话：`content/_index.md`
- **导航栏**（Home/Write）：`hugo.toml` 里的 `[menu]`
- **Frein 友链页**：`content/frein.md`

## 部署

- GitHub Pages，Source = GitHub Actions；域名 `CNAME` = `write.4587.fun`（在 `static/CNAME`）
- 主题 hugo-bearcub 已内置在 `themes/`（非 submodule），所以可以纯网页编辑
- 改完 push 即发布

## 想改主题外观

主题文件在 `themes/hugo-bearcub/layouts/`（改结构）和 `themes/hugo-bearcub/assets/`（改样式）。站点级覆盖放在根目录 `layouts/`（优先级高于主题）。
