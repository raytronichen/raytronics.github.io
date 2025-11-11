# Google 收录指南 | Google Indexing Guide

## 如何让 www.einkframe.com 被 Google 收录

### 步骤 1: 提交到 Google Search Console

1. **访问 Google Search Console**
   - 网址：https://search.google.com/search-console
   - 使用你的 Google 账号登录

2. **添加属性（Property）**
   - 点击"添加属性"
   - 选择"网址前缀"
   - 输入：`https://www.einkframe.com`
   - 点击"继续"

3. **验证网站所有权**
   
   **方法 A：HTML 文件验证（推荐）**
   - 下载验证文件
   - 将文件上传到网站根目录
   - 点击"验证"
   
   **方法 B：HTML 标签验证**
   - 复制提供的 meta 标签
   - 添加到 `_layouts/default.html` 的 `<head>` 部分
   - 点击"验证"
   
   **方法 C：DNS 验证**
   - 在域名 DNS 中添加 TXT 记录
   - 等待验证

4. **提交 Sitemap**
   - 验证成功后，进入"站点地图"
   - 输入：`https://www.einkframe.com/sitemap.xml`
   - 点击"提交"
   - Google 会自动抓取网站

### 步骤 2: 请求索引（可选但推荐）

1. 在 Search Console 中，使用"网址检查"工具
2. 输入网站首页 URL：`https://www.einkframe.com`
3. 点击"请求编入索引"
4. 对重要页面重复此操作

### 步骤 3: 等待收录

- **首次收录**：通常需要几天到几周
- **新内容收录**：通常需要几天
- **定期检查**：在 Search Console 中查看"覆盖率"报告

### 步骤 4: 优化收录速度

1. **确保 robots.txt 允许抓取**
   - 访问：https://www.einkframe.com/robots.txt
   - 确认显示：`Allow: /`

2. **确保 Sitemap 可访问**
   - 访问：https://www.einkframe.com/sitemap.xml
   - 确认可以正常访问

3. **创建高质量内容**
   - 定期发布原创内容
   - 使用相关关键词
   - 添加内部链接

4. **获取外部链接**
   - 在社交媒体分享
   - 在其他网站提及
   - 在相关论坛讨论

### 步骤 5: 监控收录状态

1. **在 Search Console 中查看**
   - "覆盖率"：查看已索引的页面
   - "性能"：查看搜索表现
   - "增强功能"：查看结构化数据

2. **使用 Google 搜索**
   - 搜索：`site:www.einkframe.com`
   - 查看返回的页面数量

### 常见问题

**Q: 提交后多久能被收录？**
A: 通常 1-4 周，但可能更快或更慢。

**Q: 为什么我的网站还没被收录？**
A: 可能原因：
- 网站太新
- 内容太少
- 没有外部链接
- robots.txt 阻止了抓取
- 网站有技术问题

**Q: 如何加快收录速度？**
A: 
- 提交 Sitemap
- 请求重要页面索引
- 创建高质量内容
- 获取外部链接
- 确保网站技术正常

### 验证工具

- **Google Search Console**: https://search.google.com/search-console
- **Google Rich Results Test**: https://search.google.com/test/rich-results
- **PageSpeed Insights**: https://pagespeed.web.dev/
- **Mobile-Friendly Test**: https://search.google.com/test/mobile-friendly

