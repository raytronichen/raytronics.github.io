# Raytronics' Blog

个人技术博客，用于分享原创的产品和技术文章。

## 技术栈

- **Jekyll**: 静态网站生成器
- **GitHub Pages**: 托管平台
- **Markdown**: 文章编写格式

## 本地开发

### 前置要求

- Ruby 2.5.0 或更高版本
- Bundler

### 安装步骤

1. 克隆仓库：
```bash
git clone https://github.com/raytronichen/raytronics.github.io.git
cd raytronics.github.io
```

2. 安装依赖：
```bash
bundle install
```

3. 启动本地服务器：
```bash
bundle exec jekyll serve
```

4. 在浏览器中访问 `http://localhost:4000`

## 添加新文章

1. 在 `_posts` 目录下创建新的 Markdown 文件
2. 文件名格式：`YYYY-MM-DD-文章标题.md`
3. 在文件开头添加 Front Matter：

```yaml
---
layout: post
title: 文章标题
date: 2025-01-20
tags: [标签1, 标签2]
---
```

4. 编写文章内容（使用 Markdown 格式）
5. 提交并推送到 GitHub，GitHub Pages 会自动构建和部署

## 目录结构

```
.
├── _config.yml          # Jekyll 配置文件
├── _layouts/            # 布局文件
│   ├── default.html     # 默认布局
│   └── post.html        # 文章布局
├── _posts/              # 文章目录
├── _includes/           # 包含文件
├── assets/              # 静态资源
│   └── css/            # 样式文件
├── about.md             # 关于页面
├── index.md             # 首页
└── README.md            # 说明文件
```

## 自定义配置

编辑 `_config.yml` 文件来自定义网站设置：

- 网站标题和描述
- 作者信息
- 社交媒体链接
- 其他 Jekyll 配置

## 许可证

MIT License

