# DeepBlue Bastion (深蓝堡垒) - 代码质量保障专家团队

## 概述

**DeepBlue Bastion** 是一个专注于**大型遗留系统维护、防御性架构设计与代码熵减管理**的虚拟精英团队。

核心KPI：**鲁棒性 (Robustness) > 可读性 (Readability) > 性能 (Performance)**

本团队假设：
- 所有输入都是恶意的
- 所有依赖都是不稳定的
- 所有代码如果不加维护都会自然腐烂

## 🚀 快速开始

### 最佳实践：使用斜杠命令触发

```
/deepblue-bastion-coordinator [你的任务描述]
```

**示例：**
```
/deepblue-bastion-coordinator 审查这段代码的安全性
/deepblue-bastion-coordinator 这个模块需要重构
/deepblue-bastion-coordinator 帮我做全面的代码质量审查
```

> 💡 **提示**：使用 `/deepblue-bastion-coordinator` 是最推荐的触发方式，协调器会自动分析任务并分配合适的专家。

## 层级架构

```
deepblue-bastion-coordinator（协调器）
├── Atlas（架构师）- 全局/结构
├── Aegis（防御专家）- 安全/防御性编程
├── Ockham（熵减专家）- 代码清洁/复杂度管理
├── BugHunter（测试官）- QA/边缘情况
├── Turbo（性能官）- 资源/并发
└── Pragmatic（务实派）- 业务/权衡
```

## 团队成员

| 代号 | 角色 | Agent 名称 | 核心职责 | 风格 |
|------|------|-----------|----------|------|
| **Atlas** | 架构师 | deepblue-bastion-atlas | 系统耦合度、模块边界、SOLID原则 | 宏观稳重，讨厌意大利面条代码 |
| **Aegis** | 防御专家 | deepblue-bastion-aegis | 边界检查、异常处理、安全防护 | 极度多疑，认为所有输入均有毒 |
| **Ockham** | 熵减专家 | deepblue-bastion-ockham | 删除死代码、简化逻辑、重构 | 极简主义，冷酷的剪刀手 |
| **BugHunter** | 测试官 | deepblue-bastion-bughunter | 边缘案例、并发冲突、脏数据 | 挑剔，总是想怎么把系统搞崩 |
| **Turbo** | 性能官 | deepblue-bastion-turbo | 内存泄漏、算法效率、资源管理 | 精打细算，对O(n²)极度敏感 |
| **Pragmatic** | 务实派 | deepblue-bastion-pragmatic | 工程落地、成本控制、业务对齐 | 现实导向，防止学术自嗨 |

## 核心特性

### 激进辩论模式 (Conflict & Consensus)

专家们不只是附和，而是会基于各自视角进行辩论：

> **Aegis**: 警告，第12行的输入没有做类型清洗，如果是注入攻击怎么办？
> **Ockham**: 同意，而且第15-20行的 if-else 嵌套太深了，建议用卫语句重构。
> **Turbo**: 但加太多校验会影响性能，我们需要权衡...
> **Pragmatic**: 方案修正：加个重试机制，但别搞太复杂，用现成的库。
> **Atlas**: 总结：采用策略模式解耦，同时补全异常捕获。

### 代码质量标准

- **代码风格**: 工业级、Google/Airbnb 规范、强类型约束
- **注释风格**: 解释"为什么"而不是"是什么"，标注潜在风险点
- **防御性编程**: 显式断言、前置条件检查、异常捕获、资源自动释放

## 任务类型映射

| 任务类型 | 触发关键词 | 主导专家 |
|----------|-----------|----------|
| 架构审查 | 架构、耦合、模块边界 | Atlas |
| 安全审计 | 安全、防御、注入 | Aegis |
| 代码熵减 | 重构、简化、死代码 | Ockham |
| 质量测试 | 测试、边缘案例、QA | BugHunter |
| 性能优化 | 性能、内存、算法 | Turbo |
| 全面审查 | 全面审查、代码审查 | 多专家辩论 |

## 安装方法

详见 [INSTALL.md](./INSTALL.md)

## 使用示例

```
用户: /deepblue-bastion-coordinator 请审查这段代码的安全性
助手: [协调器分析任务]
      → 触发 Aegis 进行安全审计
      → 触发 BugHunter 检查边缘案例
      → 综合输出审查报告

用户: /deepblue-bastion-coordinator 这个模块需要重构
助手: [协调器分析任务]
      → 触发 Atlas 评估架构影响
      → 触发 Ockham 执行熵减重构
      → 触发 Turbo 评估性能影响
      → 综合输出重构方案
```

## 文件清单

```
deepblue-bastion-team/
├── README.md                          # 团队说明
├── INSTALL.md                         # 安装指南
├── agents/
│   ├── deepblue-bastion-atlas.md      # 架构师
│   ├── deepblue-bastion-aegis.md      # 防御专家
│   ├── deepblue-bastion-ockham.md     # 熵减专家
│   ├── deepblue-bastion-bughunter.md  # 测试官
│   ├── deepblue-bastion-turbo.md      # 性能官
│   └── deepblue-bastion-pragmatic.md  # 务实派
└── skills/
    └── deepblue-bastion-coordinator/
        └── skill.md                   # 协调器
```

## License

MIT

---

## 更新日志

### 2026-02-28
- 🎉 团队配置更新到最新版本
- ✅ 优化了协调器和专家代理配置
- 📚 完善了安装指南和使用文档
