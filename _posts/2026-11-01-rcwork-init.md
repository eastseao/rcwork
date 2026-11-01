---
layout: post
title: "rcwork 开张：这个库怎么用"
tags: [说明, 用法]
---

## 这个库是干什么的

`rcwork` 是日常 markdown 的归档处：每天写出的方案、规则、复盘、笔记，统一收进一个仓库，按日期排在站点首页，随时能翻。

站点地址：<https://eastseao.github.io/rcwork/>
仓库地址：<https://github.com/eastseao/rcwork>

## 一篇新笔记怎么加

1. 在 `_posts/` 下新建文件，命名 `YYYY-MM-DD-短名.md`，日期决定它在时间轴上的位置。
2. 顶部写 front matter，最少三行：

```yaml
---
layout: post
title: "标题写中文"
tags: [标签]
---
```

3. 正文直接从 `##` 开始写，不要再用一级标题，页面标题已经是一级标题了。
4. 提交到 `main` 分支，等 Actions 跑完，刷新首页就能看到。

## 三种上传方式

| 方式 | 适合 | 代价 |
| --- | --- | --- |
| 网页 Add file | 临时补一篇 | 要手写 front matter |
| 本地 git 提交 | 批量导入旧笔记 | 要装 git、配好凭证 |
| 让助手代传 | 日常主力 | 说一句「把这篇推到 rcwork」 |

## 几个硬性约定

- 文件名用英文或拼音短名，**标题用中文写在 front matter 里**。中文文件名会让 URL 变成百分号编码，能打开但难看。
- 这是公开库，站点全网可见。含内部数据、个人信息、密钥的 md 一律不要推。
- 一篇 repo 一篇 post，不要把多天内容塞进同一个文件。
