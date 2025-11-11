# 故障排除指南 | Troubleshooting Guide

## HTTP ERROR 502 问题排查

### 快速检查清单

#### 1. 检查 DNS 配置是否正确

**使用在线工具检查：**
- https://www.whatsmydns.net
- 输入 `www.einkframe.com`
- 检查 CNAME 记录是否指向 `raytronichen.github.io`

**使用命令行检查：**
```bash
# Windows PowerShell
nslookup www.einkframe.com

# 应该看到类似这样的结果：
# www.einkframe.com canonical name = raytronichen.github.io
```

**如果 DNS 未生效：**
- 等待 5-30 分钟（DNS 传播需要时间）
- 清除本地 DNS 缓存：`ipconfig /flushdns`（Windows）

#### 2. 检查 GitHub Pages 设置

1. 访问：https://github.com/raytronichen/raytronichen.github.io/settings/pages
2. 检查 "Custom domain" 部分：
   - 应该显示 `www.einkframe.com`
   - 状态应该是 "Verified"（已验证）
   - 如果显示 "Not verified"，说明 DNS 还未生效

3. 检查 "Enforce HTTPS"：
   - 如果显示 "Not yet available"，说明 SSL 证书还在配置中
   - 等待几小时到一天时间

#### 3. 检查 Cloudflare Proxy 状态

**重要：Proxy 必须关闭！**

1. 登录 Cloudflare
2. 选择域名 `einkframe.com`
3. 进入 **DNS → Records**
4. 找到 `www` 的 CNAME 记录
5. 检查云朵图标：
   - ✅ **灰色云**（DNS only）= 正确
   - ❌ **橙色云**（Proxied）= 错误，必须关闭

**如果 Proxy 是开启的：**
1. 点击云朵图标，切换到灰色云（DNS only）
2. 等待几分钟让更改生效
3. 清除浏览器缓存

#### 4. 检查 GitHub Pages 构建状态

1. 访问：https://github.com/raytronichen/raytronichen.github.io/actions
2. 检查最近的构建是否成功
3. 如果有错误，查看错误日志

#### 5. 等待时间

**正常的时间线：**
- DNS 传播：5-30 分钟
- GitHub 验证域名：5-30 分钟
- SSL 证书配置：几小时到 24 小时

**如果超过 24 小时仍有问题，检查以下：**

### 详细诊断步骤

#### 步骤 1: 验证 DNS 记录

```bash
# 检查 CNAME 记录
dig www.einkframe.com CNAME

# 或使用 nslookup
nslookup -type=CNAME www.einkframe.com
```

**期望结果：**
```
www.einkframe.com canonical name = raytronichen.github.io
```

#### 步骤 2: 检查 GitHub Pages 状态

访问：https://github.com/raytronichen/raytronichen.github.io/settings/pages

**检查项：**
- [ ] Custom domain 显示 `www.einkframe.com`
- [ ] 状态显示 "Verified"（绿色勾）
- [ ] 没有错误提示

#### 步骤 3: 检查 SSL 证书

1. 访问：https://www.einkframe.com
2. 查看浏览器地址栏的锁图标
3. 如果显示 "不安全" 或证书错误：
   - 等待 GitHub 配置 SSL（最多 24 小时）
   - 确保 Proxy 已关闭

#### 步骤 4: 测试 GitHub 默认地址

访问：https://raytronichen.github.io

**如果这个地址可以访问：**
- 说明 GitHub Pages 本身正常
- 问题在于域名配置

**如果这个地址也无法访问：**
- 检查仓库设置
- 检查 Actions 构建状态

### 常见问题及解决方案

#### 问题 1: DNS 已配置但显示 "Not verified"

**原因：** DNS 传播还未完成

**解决：**
1. 等待 10-30 分钟
2. 使用 https://www.whatsmydns.net 检查全球 DNS 传播
3. 确保所有地区都显示正确的 CNAME 记录

#### 问题 2: 502 Bad Gateway

**可能原因：**
1. Cloudflare Proxy 开启了（最常见）
2. DNS 配置错误
3. GitHub Pages 还在处理域名验证

**解决：**
1. **立即检查并关闭 Cloudflare Proxy**
2. 等待 10-30 分钟
3. 清除浏览器缓存
4. 尝试无痕模式访问

#### 问题 3: SSL 证书错误

**原因：** GitHub 还在配置 SSL 证书

**解决：**
1. 等待 1-24 小时
2. 确保 Proxy 已关闭
3. 在 GitHub Pages 设置中启用 "Enforce HTTPS"

#### 问题 4: 网站可以访问但显示 GitHub 默认页面

**原因：** CNAME 文件可能有问题

**解决：**
1. 检查仓库根目录是否有 `CNAME` 文件
2. 文件内容应该是：`www.einkframe.com`
3. 确保文件已提交到仓库

### 验证配置成功的标志

✅ **所有以下条件都满足时，配置成功：**

1. DNS 检查工具显示 CNAME 指向 `raytronichen.github.io`
2. GitHub Pages 设置显示 "Verified"
3. 访问 `https://www.einkframe.com` 显示你的网站内容
4. 浏览器显示绿色锁图标（SSL 证书有效）
5. 没有 502 或其他错误

### 快速修复 502 错误的步骤

1. **立即检查 Cloudflare Proxy：**
   - 登录 Cloudflare
   - 找到 `www` 的 CNAME 记录
   - 确保是灰色云（DNS only）

2. **等待 10-30 分钟**

3. **清除缓存：**
   ```bash
   # Windows
   ipconfig /flushdns
   ```

4. **重新访问：**
   - 使用无痕模式
   - 或等待一段时间后重试

5. **如果仍然不行：**
   - 检查 GitHub Pages 设置
   - 查看 Actions 构建日志
   - 确认 CNAME 文件存在

### 联系支持

如果以上步骤都无法解决问题：
1. 检查 GitHub Pages 状态页面：https://www.githubstatus.com
2. 查看 GitHub 文档：https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site

