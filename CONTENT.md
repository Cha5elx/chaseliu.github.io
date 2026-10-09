# 内容维护

这是刘辰旭个人主页的内容入口。项目使用 Astro，执行 `npm run dev` 本地预览，执行 `npm run build` 生成静态站点。

## 研究成果

首页的两项研究工作在 `src/pages/index.astro` 的 `publications` 数组中。审稿状态变化时，修改对应的 `status`；期刊分级要同时核对目录年份和来源。投稿中论文只公开已获准公开的信息。

## 诗歌

24 首诗位于 `src/content/poetry/`，每首一个 Markdown 文件。文件开头包含题目、排序和原写作日期：

```md
---
title: "诗题"
order: 25
writtenDate: "2026.10.9"
---

第一行  
第二行

下一节
```

诗行末尾的两个空格用于保留 Markdown 换行。修改或新增文件后，目录和单篇页面会在构建时自动生成。根目录外的 `../Poetry/` 是迁移前的原始网页与合集，当前站点不再读取它。

## 技术博客

在 `src/content/blog/` 新建 `.md` 或 `.mdx` 文件。最少需要以下元数据：

```md
---
title: "文章标题"
description: "文章简介"
publishDate: 2026-10-09
draft: false
---

文章正文。
```

原主题的六篇示例文章已经设为 `draft: true`，不会出现在博客、文章页或 RSS 中。文章发布后会自动进入博客列表和 RSS。
