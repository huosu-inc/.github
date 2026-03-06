# 火溯（HuoSu）
专注于社区结构与真实连接构建的技术公司。

## 产品

### 千觅（Qianmi）
一款线下社区驱动，线上沟通和匹配社交平台。

## 仓库命名规则

统一格式：

`{product}-{runtime}-{profile}`

- product：产品名，例如 `qianmi`
- runtime：运行形态，例如 `service` / `web` / `miniapp` / `app`
- profile：面向的受众入口，例如 `member` / `community` / `platform`

## 分支策略
采用 Main + Feature / Fix 的简化模型。

### Main Branche
```
main
```
规则：
- 永远保持**可发布状态**
- 禁止直接 push
- 所有代码必须通过 Pull Request 合并

### 开发流程
```
需求池
   ↓
Issue
   ↓
Branch
   ↓
Pull Request
   ↓
Code Review
   ↓
base → main
```

说明：
- **Issue**：描述需求或 bug
- **Branch**：每个 Issue 建立独立分支
- **Pull Request**：开发完成提交 Pull Request
- **Reviewer**：进行代码审查与验收

### Feature Branche
用于开发新功能。
命名：
```
feat/<short-description>
```
示例：
```
feat/member-login
feat/community-create
feat/im-message-send
```

规则：
- 从 main 分支创建
- 功能开发完成后提交 PR
- 通过 Review 后合并到 main

### Fix Branche
用于修复 bug。

命名：
```
fix/<short-description>
```

示例：
```
fix/login-token-expire
fix/im-message-order
```

规则：
- 从 main 分支创建
- 修复完成提交 PR
- Review 后合并回 main

### Pull Request 规则
PR 必须满足：
- 至少 1 名 Reviewer 审查
- CI 必须通过
- 描述必须关联 Issue

Review 重点：
- Domain 设计是否合理
- 数据结构是否正确
- API 是否符合规范
- 是否引入破坏性变更

### Release
- main 达到可发布状态
- 打语义化版本标签
```
vX.Y.Z
```

示例：
```
v0.1.0
v0.2.3
v1.0.0
```

语义：
| 版本 | 含义         |
| -- | ---------- |
| X  | 大版本 / 架构变化 |
| Y  | 新功能        |
| Z  | bug 修复     |

说明：
- 服务端：X 很少变化（架构稳定）
- 客户端：版本可能随发布频繁增加
