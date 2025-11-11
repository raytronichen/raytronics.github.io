# 本地开发指南 | Local Development Guide

## 1. 本地查看网站 | Local Preview

### 前置要求 | Prerequisites

- Ruby 2.5.0 或更高版本
- Bundler

### 快速启动 | Quick Start

1. **安装依赖 | Install dependencies:**
```bash
bundle install
```

2. **启动本地服务器 | Start local server:**
```bash
bundle exec jekyll serve
```

3. **访问网站 | Access the site:**
   - 打开浏览器访问：`http://localhost:4000`
   - 修改文件后，Jekyll 会自动重新构建（可能需要刷新页面）

### 常用命令 | Common Commands

- `bundle exec jekyll serve` - 启动开发服务器
- `bundle exec jekyll serve --livereload` - 启动服务器并自动刷新浏览器
- `bundle exec jekyll build` - 构建静态网站（不启动服务器）

### 停止服务器 | Stop Server

在终端中按 `Ctrl + C` 停止服务器

## 2. 添加图片 | Adding Images

### 图片位置 | Image Location

图片放在 `pics/` 文件夹中（项目根目录）

### 在文章中使用图片 | Using Images in Posts

在 Markdown 文件中使用以下格式：

```markdown
![图片描述](/pics/图片文件名.jpg)
```

或者使用 HTML 标签获得更多控制：

```html
<img src="/pics/图片文件名.jpg" alt="图片描述" style="max-width: 100%;">
```

### 示例 | Example

```markdown
![Mona Lisa pixel view](/pics/monalisa_pixel.jpg)
```

### 支持的图片格式 | Supported Formats

- JPG/JPEG
- PNG
- GIF
- WebP

## 3. 添加新文章 | Adding New Posts

1. 在 `_posts/` 目录下创建新文件
2. 文件名格式：`YYYY-MM-DD-文章标题.md`
3. 文件开头添加 Front Matter：

```yaml
---
layout: post
title: 文章标题
date: 2025-01-21
tags: [标签1, 标签2]
---
```

4. 编写文章内容（Markdown 格式）
5. 保存后，本地服务器会自动更新

