
# 部署到 Vercel 指南

本项目已经配置好可以直接部署到 Vercel。

## 前置要求

1. 一个 Vercel 账户（可以通过 GitHub、GitLab 或 Bitbucket 注册）
2. 代码推送到 GitHub、GitLab 或 Bitbucket 仓库

## 部署步骤

### 方法一：通过 Vercel 网站部署

1. 访问 [vercel.com](https://vercel.com) 并登录
2. 点击 "New Project" 按钮
3. 导入您的代码仓库
4. 配置项目设置：
   - Framework Preset: Other
   - Root Directory: ./ (保持默认)
   - Build Command: 留空
   - Output Directory: 留空
5. 点击 "Deploy" 按钮开始部署

### 方法二：通过 Vercel CLI 部署

1. 安装 Vercel CLI：
   ```bash
   npm i -g vercel
   ```

2. 在项目根目录运行：
   ```bash
   vercel
   ```

3. 按照提示操作，完成部署

## 环境变量配置

在 Vercel 项目设置中添加以下环境变量（可选）：

- `ADMIN_PASSWORD`: 管理员登录密码（默认为"你想要的密码"）

## 部署后访问

部署完成后，Vercel 会提供一个 URL，您可以通过这个 URL 访问您的应用。

## 注意事项

1. 本项目使用内存存储数据，因此在 Vercel 的无服务器环境中，数据不会持久化。每次函数重新部署或冷启动时，数据会重置为默认值。

2. 如果您需要持久化数据存储，建议使用 Vercel 的集成服务，如：
   - Vercel Postgres
   - Upstash Redis
   - Supabase

3. 本项目已经配置了 API 路由和静态文件路由，无需额外配置。

## 故障排除

如果遇到 404 错误：

1. 检查 `vercel.json` 文件是否正确配置
2. 确认 `api/index.js` 文件正确导出了 Express 应用
3. 查看 Vercel 部署日志，检查是否有错误信息
