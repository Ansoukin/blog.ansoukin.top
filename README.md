# blog.ansoukin.top

我的个人博客 —— Hexo + Qexo。

## 本地开发

```bash
pnpm install        # 首次或依赖变更后
pnpm server         # 预览 http://localhost:4000，改文件自动刷新
pnpm new "标题"     # 新建文章，写到 source/_posts/
```

## 发布

```bash
pnpm deploy         # clean → generate → 推送 gh-pages
```

推送完成后 GitHub Actions/Pages 会自动更新，一两分钟内生效。

## 分支说明

| 分支 | 内容 |
| --- | --- |
| `main` | Hexo 源码：`_config.yml`、`source/`、`themes/` |
| `gh-pages` | `hexo generate` 的产物，GitHub Pages 从这里发布 |

`gh-pages` 由 `hexo-deployer-git` 自动生成，**不要手动改**，下次部署会被覆盖。

## 自定义域名

`source/CNAME` 里写着 `blog.ansoukin.top`，构建时复制到站点根目录。换域名要同时改这个文件和 `_config.yml` 的 `url`。

## Qexo 后台

Qexo 通过 GitHub API 直接读写 `main` 分支的 Markdown，所以它的仓库配置要指向 `Ansoukin/blog.ansoukin.top`、分支 `main`、文章目录 `source/_posts`。
