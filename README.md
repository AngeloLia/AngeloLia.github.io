# 旧雨楼

少年听雨歌楼上。

个人记录博客：杂谈、读书笔记、音谋笔记和游记。由 Hugo + PaperMod 构建，托管在 GitHub Pages 上。

- 站点：https://angelolia.github.io/
- 仓库：https://github.com/AngeloLia/AngeloLia.github.io

## 技术栈

- Hugo（扩展版，0.147.9）+ PaperMod 主题
- GitHub Actions 自动构建并部署到 GitHub Pages
- 主题不在仓库里存放，构建时由工作流从 `adityatelange/hugo-PaperMod` 拉取

## 本地预览

```bash
# 安装 Hugo 扩展版，并拉取主题
git clone --depth 1 https://github.com/adityatelange/hugo-PaperMod themes/PaperMod

# 本地预览
hugo server -D
```

## 写文章

```bash
# 新建一篇
hugo new content content/posts/2025-11-12-title/index.md

# 写完发布：提交并推送，Actions 自动上线
git add .
git commit -m "post: 标题"
git push
```

也可以直接在 GitHub 网页端新建或编辑 Markdown 文件，保存即触发部署。

草稿用头信息里的 `draft: true` 标记，未写完的文章不会被发布，写完改成 `false` 即可。

文章头信息格式：

```yaml
---
title: "文章标题"
date: 2025-11-12T20:00:00+08:00
draft: false
categories: ["杂谈"]
tags: ["记录"]
---
```

## 图片

- 文章配图：图片先压缩到长边不超过 1920 像素，尽量转 WebP，按 `日期-主题-序号` 命名；小图放进仓库的 `static/images/` 或文章页面包，大图建议放图床后在文章里引用链接。
- 仓库超过 500 MB 时，先把历史大图迁到图床再继续写。

## WordPress 迁移

旧站文章由 WordPress 导出文件 `WordPress.2025-05-12.xml` 转换而来，逐篇对照见 `MIGRATION.md`。已迁移 6 篇已发布文章；草稿、回收站内容、私密文章和页面均未导入。

自定义域名以后再加：在域名商处解析到 GitHub Pages，并在仓库里加 `static/CNAME` 文件（目前没有自定义域名，不要建这个文件）。
