# Next.js 邮件客户端

一个基于 Next.js 15 的现代化邮件客户端应用，支持多账号管理、实时邮件同步和发送功能。

## 🚀 功能特性

- **多账号管理**: 支持添加和管理多个邮件账号
- **实时同步**: 自动获取最新邮件，支持增量更新
- **邮件发送**: 支持发送邮件，包括抄送和密送
- **搜索过滤**: 强大的邮件搜索和过滤功能
- **响应式设计**: 适配桌面和移动设备
- **实时通知**: 新邮件实时通知（可开关）
- **缓存优化**: 智能缓存机制，提升用户体验

## 🛠️ 技术栈

- **前端**: Next.js 15 + React 19 + TypeScript 5
- **UI 组件**: shadcn/ui + Tailwind CSS 4
- **数据库**: Prisma 6 + SQLite
- **实时通信**: Socket.IO
- **状态管理**: Zustand + TanStack Query
- **表单处理**: React Hook Form + Zod

## 📦 快速开始

### 环境要求
- Node.js 18+ 
- npm 或 yarn

### 安装依赖
```bash
npm install
```

### 环境配置
复制并配置环境变量：
```bash
cp .env.example .env
```

编辑 `.env` 文件（可选）：
```env
# 数据库配置 (可选)
DATABASE_URL="file:./db/custom.db"

# 应用环境
NODE_ENV=development
```

### 数据库初始化
```bash
npm run db:push
npm run db:generate
```

### 开发运行
```bash
npm run dev
```

访问 http://localhost:3000

### 构建部署
```bash
npm run build
npm start
```

## 🚀 部署到 Render

### 自动部署（推荐）
1. 确保项目包含 `render.yaml` 配置文件
2. 在 Render 控制台创建新的 Web Service
3. 连接 GitHub 仓库
4. Render 会自动检测配置并部署

### 手动部署
1. 在 Render 控制台创建 Web Service
2. 连接 GitHub 仓库 `runfeng771/em17`
3. 配置构建设置：
   - **Build Command**: `npm install && npm run build`
   - **Start Command**: `npm start`
4. 设置环境变量：
   ```env
   NODE_ENV=production
   DATABASE_URL=file:./db/custom.db
   ```

## 📁 项目结构

```
src/
├── app/                 # Next.js App Router
│   ├── api/            # API 路由
│   ├── page.tsx        # 主页面
│   ├── layout.tsx     # 布局组件
│   └── globals.css     # 全局样式
├── components/         # React 组件
│   └── ui/            # shadcn/ui 组件
├── lib/               # 工具库
│   ├── db.ts          # 数据库配置
│   ├── utils.ts       # 工具函数
│   ├── socket.ts      # Socket.IO 配置
│   └── email-service.ts  # 邮件服务
└── hooks/             # React Hooks
```

## 🔧 配置说明

### 数据库配置
项目使用 SQLite 数据库，默认路径为 `file:./db/custom.db`。数据库文件会自动创建和初始化。

### 邮件服务器配置
支持标准的 IMAP/SMTP 邮件服务器，默认配置为：
- IMAP 服务器: `imap.email.cn:993`
- SMTP 服务器: `smtp.email.cn:465`

### 环境变量
- `NODE_ENV`: 应用环境 (development/production)
- `DATABASE_URL`: 数据库连接 URL
- `IMAP_SERVER`: IMAP 服务器地址
- `IMAP_PORT`: IMAP 服务器端口
- `SMTP_SERVER`: SMTP 服务器地址
- `SMTP_PORT`: SMTP 服务器端口

## 📖 使用指南

### 添加邮件账号
1. 点击"添加账号"按钮
2. 填写邮箱地址和密码
3. 配置 IMAP/SMTP 服务器信息（可选）
4. 保存配置

### 获取邮件
- 单个账号刷新：点击账号旁边的刷新按钮
- 批量刷新：使用"强制刷新全部"功能
- 自动刷新：系统每8秒自动检查新邮件

### 发送邮件
1. 点击"撰写邮件"按钮
2. 填写收件人、主题和内容
3. 可添加抄送和密送
4. 点击发送

### 搜索邮件
使用搜索框可以按主题、发件人或内容搜索邮件。

## 🛡️ 安全考虑

- 密码加密存储
- 环境变量管理敏感信息
- 数据库文件本地存储
- HTTPS 加密传输

## 📊 性能优化

- 增量邮件同步，避免重复获取
- 智能缓存机制，提升响应速度
- 异步邮件发送，不阻塞用户界面
- 优化的数据库查询

## 🤝 贡献指南

1. Fork 项目
2. 创建功能分支
3. 提交更改
4. 推送到分支
5. 创建 Pull Request

## 📄 许可证

MIT License

## 🆘 支持

如有问题，请通过以下方式联系：
- GitHub Issues
- 邮件支持

---

**最后更新**: 2024年8月25日