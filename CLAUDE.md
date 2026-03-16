# EMall Frontend Web - 项目说明

## 项目概述

这是一个基于 Vue 3 + Vite + TypeScript 的电商前端项目，使用现代化的前端技术栈构建。

## 技术栈

- **核心框架**: Vue 3.5.22
- **构建工具**: Vite 7.1.7
- **语言**: TypeScript 5.9.3
- **路由**: Vue Router 4.6.3
- **UI 组件库**:
  - Element Plus 2.11.5
  - Vue Amazing UI 2.4.22
  - Ant Design Icons Vue 7.0.1
- **HTTP 客户端**: Axios 1.12.2
- **包管理器**: pnpm

## 项目结构

```
emall-frontend-web/
├── src/
│   ├── assets/          # 静态资源
│   ├── common/          # 公共组件（如 Buttons.vue）
│   ├── components/      # 可复用组件
│   │   ├── HelloWorld.vue
│   │   ├── Search.vue
│   │   ├── SearchPage.vue
│   │   └── TableTemplate.vue
│   ├── constants/       # 常量定义
│   ├── layout/          # 布局组件
│   │   ├── ContainerLayout.vue
│   │   └── RootLayout.vue
│   ├── menu/            # 菜单组件
│   │   ├── CustomMenu.vue
│   │   └── DefaultMenu.vue
│   ├── router/          # 路由配置
│   ├── views/           # 页面视图
│   │   ├── cart/        # 购物车
│   │   ├── home/        # 首页
│   │   ├── item/        # 商品详情
│   │   ├── login/       # 登录
│   │   ├── order/       # 订单
│   │   ├── register/    # 注册
│   │   └── search/      # 搜索
│   ├── App.vue          # 根组件
│   ├── main.ts          # 应用入口
│   └── style.css        # 全局样式
├── public/              # 公共静态资源
├── vite.config.ts       # Vite 配置
├── tsconfig.json        # TypeScript 配置
└── package.json         # 项目依赖
```

## 路径别名配置

项目已配置以下路径别名，可在导入时使用：

- `@` → `./src`
- `@components` → `./src/components`
- `@views` → `./src/views`
- `@utils` → `./src/utils`
- `@api` → `./src/api`
- `@assets` → `./src/assets`
- `@stores` → `./src/stores`
- `@types` → `./src/types`
- `@styles` → `./src/styles`

## 路由配置

项目使用 Vue Router 进行页面导航，已配置的路由：

- `/` - 首页
- `/search` - 商品搜索
- `/login` - 用户登录
- `/register` - 用户注册
- `/item/:id` - 商品详情（动态路由）
- `/order` - 订单列表
- `/cart` - 购物车

## 开发规范

### 命名规范

- **组件**: 使用 PascalCase（如 `HelloWorld.vue`）
- **文件夹**: 使用 kebab-case（如 `user-profile/`）
- **变量/函数**: 使用 camelCase（如 `userName`）
- **常量**: 使用 UPPER_SNAKE_CASE（如 `API_BASE_URL`）

### 组件开发

1. **组件位置**:
   - 公共可复用组件 → `src/components/`
   - 页面级组件 → `src/views/`
   - 布局组件 → `src/layout/`
   - 通用业务组件 → `src/common/`

2. **组件自动导入**: 项目使用 `unplugin-vue-components` 自动导入 Vue Amazing UI 组件，无需手动引入

3. **样式**: 优先使用 UI 组件库提供的组件和样式，保持界面一致性

### TypeScript

- 启用严格模式
- 为组件 props、emits、状态等添加类型定义
- 避免使用 `any`，使用 `unknown` 或具体类型

### Git 工作流

- 主分支: `main`
- 开发分支: `dev`
- 功能分支命名: `feature/功能名称`
- 修复分支命名: `fix/问题描述`

## 常用命令

```bash
# 安装依赖
pnpm install

# 启动开发服务器
pnpm dev

# 构建生产版本
pnpm build

# 预览生产构建
pnpm preview
```

## 开发注意事项

1. **路由导航**: 使用 `router.push()` 或 `<router-link>` 进行页面跳转
2. **HTTP 请求**: 统一使用 axios 进行 API 调用，建议在 `src/api/` 目录下封装 API 接口
3. **状态管理**: 如需全局状态管理，可在 `src/stores/` 目录下使用 Pinia（需先安装）
4. **类型定义**: 在 `src/types/` 目录下统一管理 TypeScript 类型定义
5. **工具函数**: 在 `src/utils/` 目录下放置公共工具函数

## 待完善目录

以下目录已在路径别名中配置，但尚未创建，开发时可按需创建：

- `src/api/` - API 接口封装
- `src/utils/` - 工具函数
- `src/stores/` - 状态管理
- `src/types/` - 类型定义
- `src/styles/` - 样式文件

## 代码提交规范

使用约定式提交（Conventional Commits）：

- `feat:` 新功能
- `fix:` 修复 bug
- `docs:` 文档更新
- `style:` 代码格式调整
- `refactor:` 重构代码
- `perf:` 性能优化
- `test:` 测试相关
- `chore:` 构建/工具链相关

示例：`feat: 添加用户个人中心页面`
