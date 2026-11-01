# rcwork

日常 markdown 归档库。所有笔记按发布日期归档，推到 `main` 后由 GitHub Actions 自动构建成站点。

- 站点：https://eastseao.github.io/rcwork/
- 归档页：https://eastseao.github.io/rcwork/archive/
- Feed：https://eastseao.github.io/rcwork/feed.xml

## 目录结构

```
_config.yml                    站点配置（标题、baseurl、主题、插件）
index.md                       首页，列出全部笔记
archive.md                     归档页，按年月分组
about.md                       关于页
_posts/                        正文在这里，一篇一个文件
_includes/custom-head.html     挂自定义样式
assets/css/custom.css          自定义样式
.github/workflows/pages.yml    推送即自动构建部署
```

## 新增一篇笔记

1. 在 `_posts/` 下新建 `YYYY-MM-DD-short-name.md`，日期就是它的发布时间。
2. 顶部写 front matter：

```yaml
---
layout: post
title: "中文标题写这里"
tags: [标签]
---
```

3. 正文从 `##` 起笔，别再用一级标题。
4. 提交到 `main`，等 Actions 跑完（约 1 分钟），首页自动出现。

## 上传方式

| 方式 | 适用 | 说明 |
| --- | --- | --- |
| 让助手代传 | 日常主力 | 说一句「把这篇推到 rcwork」，自动补 front matter、定名、提交 |
| 网页 Add file | 临时补一篇 | 需自己写 front matter |
| 本地 git | 批量导入旧笔记 | `git clone` 后复制进 `_posts/`，`git push` |

## 约定

- **文件名用英文/拼音短名，中文标题放 front matter 的 `title`**。中文文件名会让 URL 变成百分号编码。
- 一篇文件一篇 post，不要在一个文件里堆多天内容。
- 随手丢到其他目录的 `.md` 也会被渲染成页面，但不会进首页列表；`README.md` 已排除。

## 注意

这是**公开库**，站点内容全网可见。涉及内部数据、个人信息、密钥、未脱敏客户资料的 md 不要推上来；需要收录时改用私有库或先脱敏。

## 本地预览（可选，非必需）

需要 Ruby + Jekyll 环境：

```bash
gem install github-pages
bundle exec jekyll serve
```

Windows 上装 Ruby 比较折腾，不预览也能直接推送看线上效果。
