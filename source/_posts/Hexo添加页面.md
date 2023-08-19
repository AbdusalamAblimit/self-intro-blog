---
title: Hexo添加页面
date: 2023-08-19 18:27:04
tags:
- Hexo
- 博客
categories:
- 博客搭建
- Hexo框架
---

## 添加“关于”页面
首先通过一下命令生成新页面：
```bash
hexo new page "about"
```

此时会在**source**目录下生成about/index.md，在这里编写Markdown即可。

除此之外好像还可以将其修改为index.html然后写html页面。


## 添加“分类”页面
首先通过一下命令生成新页面：
```
hexo new page "categories"
```


修改 `source/categories/index.md`的内容如下：

```markdown
---
title: 分类
date: 2023-08-19 18:34:46
type: "categories"
---
```

此时“分类”页面就完成了，在这个markdown里写其他内容也不会再显示了。


## 添加“标签”页面
```
hexo new page "tags"
```


修改 `source/tags/index.md`的内容如下：

```markdown
---
title: 标签
date: 2023-08-19 18:34:46
type: "tags"
---
```

跟“分类”页面一样，在这个页面写的其他内容都不会显示。