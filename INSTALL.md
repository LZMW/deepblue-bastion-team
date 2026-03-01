# DeepBlue Bastion (深蓝堡垒) 安装指南

> **版本**: 3.0
> **更新日期**: 2026-03-01

---

## 📋 安装前准备

### 系统要求

- Claude Code CLI（最新版本）
- 有效的Claude API访问权限
- 支持的操作系统：Windows / macOS / Linux

### 必要条件

- 已安装 Claude Code
- 已配置 Claude API密钥
- 有写入用户技能目录的权限

---

## 🚀 快速安装

### 方法1：自动安装（推荐）

1. **复制配置包到目标位置**

配置包已准备在：
```
N:\编程备份\3.0团队\deepblue-bastion-team\
```

2. **确认安装路径**

Claude Code技能目录：
- **Windows**: `C:\Users\[用户名]\.claude\skills\`
- **macOS/Linux**: `~/.claude/skills/`

3. **复制协调器Skill**

```bash
# Windows
xcopy /E /I "N:\编程备份\3.0团队\deepblue-bastion-team\skills\deepblue-bastion-coordinator" "C:\Users\[用户名]\.claude\skills\deepblue-bastion-coordinator\"

# macOS/Linux
cp -r "N:\编程备份\3.0团队\deepblue-bastion-team\skills\deepblue-bastion-coordinator" ~/.claude/skills/
```

4. **复制专家Agent配置**

```bash
# Windows
xcopy /E /I "N:\编程备份\3.0团队\deepblue-bastion-team\agents" "C:\Users\[用户名]\.claude\agents\deepblue-bastion\"

# macOS/Linux
cp -r "N:\编程备份\3.0团队\deepblue-bastion-team\agents" ~/.claude/agents/deepblue-bastion/
```

5. **验证安装**

在Claude Code中执行：
```bash
"使用深蓝堡垒团队审查这个代码库"
```

---

## 📂 详细安装说明

### 安装目录结构

安装后的目录结构应如下：

```
~/.claude/                              # Claude Code根目录
├── skills/                             # Skills目录
│   └── deepblue-bastion-coordinator/   # 协调器Skill
│       └── skill.md                    # 协调器配置文件
└── agents/                             # Agents目录
    └── deepblue-bastion/               # 深蓝堡垒团队
        ├── deepblue-bastion-atlas.md
        ├── deepblue-bastion-aegis.md
        ├── deepblue-bastion-ockham.md
        ├── deepblue-bastion-bughunter.md
        ├── deepblue-bastion-turbo.md
        └── deepblue-bastion-pragmatic.md
```

---

## 🔍 验证安装

### 1. 检查文件完整性

确认以下文件已正确安装：

**协调器**：
- [ ] `~/.claude/skills/deepblue-bastion-coordinator/skill.md`

**专家代理**（6个）：
- [ ] `~/.claude/agents/deepblue-bastion/deepblue-bastion-atlas.md`
- [ ] `~/.claude/agents/deepblue-bastion/deepblue-bastion-aegis.md`
- [ ] `~/.claude/agents/deepblue-bastion/deepblue-bastion-ockham.md`
- [ ] `~/.claude/agents/deepblue-bastion/deepblue-bastion-bughunter.md`
- [ ] `~/.claude/agents/deepblue-bastion/deepblue-bastion-turbo.md`
- [ ] `~/.claude/agents/deepblue-bastion/deepblue-bastion-pragmatic.md`

### 2. 功能测试

在Claude Code中测试协调器：

```bash
# 测试1：简单触发
"使用深蓝堡垒团队审查这个文件"

# 测试2：特定任务
"使用深蓝堡垒的安全专家检查这个代码的安全漏洞"

# 测试3：全面审查
"使用深蓝堡垒团队对代码库进行全面审查"
```

### 3. 验证输出

检查是否在项目根目录生成 `.dbb/` 工作目录：
```bash
ls -la .dbb/
```

预期输出：
```
drwxr-xr-x  phases/
drwxr-xr-x  outputs/
-rw-r--r--  inbox.md
-rw-r--r--  summary.md
```

---

## 🛠️ 配置说明

### 协调器配置

协调器Skill配置文件：`skill.md`

**关键字段**：
```yaml
name: deepblue-bastion-coordinator
description: DeepBlue Bastion (深蓝堡垒) team coordinator skill...
```

### 专家Agent配置

每个专家Agent配置文件包含：

**YAML Front Matter**：
```yaml
---
name: deepblue-bastion-[expert-name]
description: "Use this agent when you need to..."
tools: Read, Glob, Grep, Write, Edit
---
```

**正文内容**：
- 核心原则
- 调度指令理解
- 信息传递机制
- 专业职责
- 工作流程
- 输出规范

---

## ⚙️ 高级配置

### MCP工具配置（可选）

如果需要使用MCP咨询工具，确保：

1. **Aegis安全专家**：可使用 `consult_aurai` 咨询安全策略
2. **Turbo性能专家**：可使用 `consult_aurai` 咨询性能优化

配置方式：在触发任务时同意使用MCP工具。

---

## 🔧 故障排查

### 问题1：协调器无法触发

**症状**：输入指令后没有任何响应

**可能原因**：
- Skill配置文件路径错误
- description格式错误

**解决方案**：
1. 检查文件是否在正确位置：`~/.claude/skills/deepblue-bastion-coordinator/skill.md`
2. 确认description无双引号、单行格式
3. 重启Claude Code

### 问题2：专家代理无法启动

**症状**：协调器尝试触发专家，但失败

**可能原因**：
- Agent配置文件路径错误
- description格式错误

**解决方案**：
1. 检查文件是否在正确位置：`~/.claude/agents/deepblue-bastion/`
2. 确认description使用双引号、单行格式
3. 检查tools字段是否正确

### 问题3：输出目录混乱

**症状**：`.dbb/`目录结构不符合预期

**可能原因**：
- 执行模式识别错误
- 路径配置错误

**解决方案**：
1. 检查协调器的模式识别逻辑
2. 清理 `.dbb/` 目录，重新执行
3. 使用串行模式测试基本功能

### 问题4：MCP工具无法使用

**症状**：专家无法使用授权的MCP工具

**可能原因**：
- MCP工具未正确配置
- 授权流程未完成

**解决方案**：
1. 确认MCP服务已正确配置
2. 检查授权流程是否完成
3. 使用基础工具替代

---

## 📋 升级指南

### 从旧版本升级

1. **备份旧版本**（可选）
```bash
mv ~/.claude/skills/deepblue-bastion-coordinator ~/.claude/skills/deepblue-bastion-coordinator.bak
mv ~/.claude/agents/deepblue-bastion ~/.claude/agents/deepblue-bastion.bak
```

2. **安装新版本**
按照上述安装步骤执行。

3. **验证升级**
执行功能测试，确认一切正常。

4. **删除备份**（确认无问题后）
```bash
rm -rf ~/.claude/skills/deepblue-bastion-coordinator.bak
rm -rf ~/.claude/agents/deepblue-bastion.bak
```

---

## 🗑️ 卸载指南

### 完全卸载

1. **删除协调器Skill**
```bash
rm -rf ~/.claude/skills/deepblue-bastion-coordinator
```

2. **删除专家Agent**
```bash
rm -rf ~/.claude/agents/deepblue-bastion
```

3. **清理工作目录**（可选）
```bash
rm -rf .dbb/
```

---

## 📞 技术支持

### 获取帮助

1. **查看README.md**
   - 团队介绍
   - 使用方法
   - 最佳实践

2. **检查配置文件**
   - 协调器：`skill.md`
   - 专家：`deepblue-bastion-*.md`

3. **查看日志**
   - 检查Claude Code输出
   - 查看 `.dbb/inbox.md` 消息

### 常见问题

**Q：安装后无法触发团队？**
A：检查文件路径和权限，确保配置文件在正确位置。

**Q：专家代理输出异常？**
A：检查description格式，确认使用双引号和单行格式。

**Q：如何重置配置？**
A：删除 `.dbb/` 工作目录，重新触发任务。

---

## 📝 配置清单

### 安装完成检查表

- [ ] 协调器Skill已安装
- [ ] 6个专家Agent已安装
- [ ] 文件路径正确
- [ ] 功能测试通过
- [ ] 工作目录正常生成

### 配置验证清单

- [ ] 协调器description无双引号
- [ ] Agent description使用双引号
- [ ] tools字段配置正确
- [ ] 信息传递机制嵌入
- [ ] MCP授权机制完整

---

## 🎉 安装完成

安装完成后，您就可以开始使用DeepBlue Bastion团队了！

### 快速开始

在Claude Code中输入：
```bash
"使用深蓝堡垒团队审查这个代码库"
```

协调器会自动：
1. 分析任务需求
2. 选择执行模式
3. 触发相应专家
4. 汇总分析结果

---

**祝您使用愉快！**

**DeepBlue Bastion Team v3.0**
**Last Updated: 2026-03-01**
