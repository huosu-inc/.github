# 火溯（HuoSu）

专注于社区结构与真实连接构建的技术公司。

## 产品

### 千觅（Qianmi）
一款线下社区驱动，线上沟通和匹配社交平台。

## 仓库命名规则

统一格式：

`{product}-{runtime}-{profile}`

- product：产品名，例如 `qianmi`
- runtime：运行形态，例如 `backend` / `web` / `miniapp` / `app`
- profile：面向的受众入口，例如 `member` / `community` / `platform`

## 分支策略
- Main branches:
    - `main` – production-ready code.
    - `dev` – integration branch

- `main` 和 `dev` 分支禁止直接提交
    - 所有更改必须通过 Pull Requests

### Dev-{person} 分支策略
长线开发可以用个人从开发分支检出的方式。一次合并多个模块的代码。
一般维护推荐一个功能一个分支的方式。

### Feature 分支
- 命名：`feature/<short-description>`
- 来源分支：从 `dev` 分支检出
- 合并目标：开发完成后合并回 `dev` 分支

### Hotfix 分支
- 命名：`hotfix/<short-description>`
- 来源分支：从 `main` 分支检出
- 合并目标：修复完成后同时合并到 `main` 和 `dev`

### 发版流程
1. 通过 Pull Request 将 `dev` 合并到 `main`
2. 使用语义化版本打标签，格式：`vX.Y.Z`（如 `v0.1.0`）
   - 服务端的 X 一般很稳定，除非项目出现大规模重构。
   - 客户端，特别 app 的每次变化基本是累加 X
