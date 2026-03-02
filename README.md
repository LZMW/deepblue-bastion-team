# DeepBlue Bastion (深蓝堡垒) 团队

> 🔷 **技术委员会主理AI，统筹六位专家对代码或架构方案进行无情解构、清洗与重铸**

---

## 团队简介

DeepBlue Bastion 是一个专业的代码质量与架构优化团队，由6位专家组成，采用**并行辩论模式**进行代码审查和优化。

### 核心KPI

**鲁棒性 (Robustness) > 可读性 (Readability) > 性能 (Performance)**

---

## 团队成员

| 代号 | 角色 | 核心关注 | 颜色 |
|------|------|----------|------|
| **Atlas** | 架构师 | 系统耦合度、模块边界、SOLID原则 | 🟠 Orange |
| **Aegis** | 防御专家 | 边界检查、异常处理、安全防护 | 🔴 Red |
| **Ockham** | 熵减专家 | 删除死代码、简化逻辑、重构 | 🔵 Blue |
| **BugHunter** | 测试官 | 边缘案例、并发冲突、脏数据 | 🟢 Green |
| **Turbo** | 性能官 | 内存泄漏、算法效率、资源管理 | 🟡 Yellow |
| **Pragmatic** | 务实派 | 工程落地、成本控制、业务对齐 | 🟣 Purple |

---

## 使用方法

### 触发协调器

```
/deepblue-bastion-coordinator
```

### 典型使用场景

1. **全面代码审查**
   ```
   /deepblue-bastion-coordinator 对这段代码进行全面审查
   ```

2. **安全审计**
   ```
   /deepblue-bastion-coordinator 帮我做安全审计
   ```

3. **性能优化**
   ```
   /deepblue-bastion-coordinator 这个函数太慢了，帮我优化
   ```

4. **代码重构**
   ```
   /deepblue-bastion-coordinator 这段代码太复杂，帮我简化
   ```

---

## 执行模式

### 单专家模式

用户只需要某一方面的专业审查时，协调器会触发单个专家。

### 并行辩论模式（默认）

全面审查时，协调器会**同时触发所有专家**进行独立分析：

```
┌─────────────┐
│  协调器     │
└──────┬──────┘
       │ 并行触发
       ▼
┌──────────────────────────────────────┐
│  Atlas  │ Aegis │ Ockham │ BugHunter │ Turbo │ Pragmatic │
└────┬─────┴───┬───┴───┬────┴────┬─────┴───┬──┴─────┬─────┘
     │         │       │          │         │        │
     └─────────┴───────┴──────────┴─────────┴────────┘
                          │
                          ▼
                   ┌──────────────┐
                   │ Atlas 综合   │
                   └──────────────┘
```

---

## 辩论示例

```markdown
> **Aegis**: 警告，第12行的输入没有做类型清洗，如果是注入攻击怎么办？
> **Ockham**: 同意，而且第15-20行的 if-else 嵌套太深了，建议用卫语句重构。
> **Turbo**: 但加太多校验会影响性能...
> **Pragmatic**: 用现成的库，别重复造轮子。
> **Atlas**: 总结：采用策略模式解耦，同时补全异常捕获。
```

---

## 产出结构

```
{项目}/.deepblue/
├── outputs/                   # 并行产出
│   ├── atlas/                # Atlas 架构分析
│   ├── aegis/                # Aegis 安全审计
│   ├── ockham/               # Ockham 熵减分析
│   ├── bughunter/            # BugHunter 测试设计
│   ├── turbo/                # Turbo 性能分析
│   └── pragmatic/            # Pragmatic 可行性评估
├── inbox.md                   # 统一消息收件箱（辩论记录）
└── summary.md                 # 最终汇总（由 Atlas 综合）
```

---

## MCP工具授权

| 专家 | 可授权的MCP工具 | 授权条件 |
|------|-----------------|----------|
| Atlas | sequential-thinking, context7 | 架构分析需要深度推导或查询架构模式时 |
| Aegis | 无 | 不使用MCP |
| Ockham | 无 | 不使用MCP |
| BugHunter | context7 | 测试设计需要查询最佳实践时 |
| Turbo | sequential-thinking, context7 | 性能分析需要复杂推导或查询优化方案时 |
| Pragmatic | sequential-thinking | 权衡评估需要深度思考时 |

---

## 代码标准

- **风格**：工业级、Google/Airbnb 规范、强类型约束
- **注释**：解释"为什么"而非"是什么"
- **防御性**：显式断言、前置条件、异常捕获、资源自动释放

---

## 目标受众

资深技术 Tech Lead 或架构师，需要 Production Ready 的代码。

---

## 版本信息

- **版本**：4.0
- **生成工具**：super-team-builder v3.2
- **生成日期**：2026-03-02
