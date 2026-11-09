---
title: 开始写作
date: 2026-11-09 20:45:00
tags:
  - 随笔
categories:
  - 公告
---

博客搭好了，第一篇先记点有用的东西：这个站怎么运转的，以后自己回头看不用再翻文档。

## 写作与发布

```bash
pnpm new "文章标题"   # 在 source/_posts/ 下生成 md
pnpm server           # 本地预览 http://localhost:4000
pnpm deploy           # 生成并推送到 gh-pages
```

写作就是写 Markdown，保存后预览页会自动刷新。

## 站点结构

- `main` 分支放源码：配置、文章、主题
- `gh-pages` 分支放生成的静态页面，GitHub Pages 从这里取内容
- 域名 `blog.ansoukin.top` 通过 `source/CNAME` 绑定，构建时会被复制到站点根目录

## 代码块效果

```javascript
const posts = await hexo.locals.get('posts');
posts.forEach(post => console.log(post.title));
```

改主题、加插件都只需要动 `_config.yml` 和 `package.json`，然后重新 `pnpm deploy`。
