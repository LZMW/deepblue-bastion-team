# DeepBlue Bastion 安装指南

## 前置要求

- Claude Code CLI 已安装
- 工作目录: `~/.claude/` (Windows: `C:\Users\[用户名]\.claude\`)

## 安装步骤

### 方法一：手动复制（推荐）

1. **复制 Agent 配置**

```bash
# Windows (Git Bash)
cp -r deepblue-bastion-team/agents/* ~/.claude/agents/

# 或手动复制
# 将 agents/ 目录下的 6 个 .md 文件复制到:
# C:\Users\[用户名]\.claude\agents\
```

2. **复制 Skill 配置**

```bash
# Windows (Git Bash)
cp -r deepblue-bastion-team/skills/deepblue-bastion-coordinator ~/.claude/skills/

# 或手动复制
# 将 skills/deepblue-bastion-coordinator/ 目录复制到:
# C:\Users\[用户名]\.claude\skills\
```

3. **验证目录结构**

安装后应如下：

```
~/.claude/
├── agents/
│   ├── deepblue-bastion-atlas.md
│   ├── deepblue-bastion-aegis.md
│   ├── deepblue-bastion-ockham.md
│   ├── deepblue-bastion-bughunter.md
│   ├── deepblue-bastion-turbo.md
│   └── deepblue-bastion-pragmatic.md
└── skills/
    └── deepblue-bastion-coordinator/
        └── skill.md
```

### 方法二：命令行一键安装

```bash
# 进入团队目录
cd deepblue-bastion-team

# 创建目标目录
mkdir -p ~/.claude/agents ~/.claude/skills

# 复制文件
cp agents/*.md ~/.claude/agents/
cp -r skills/deepblue-bastion-coordinator ~/.claude/skills/
```

## 验证安装

1. **重启 Claude Code**

```bash
# 退出当前会话，重新启动 Claude Code
```

2. **测试触发**

在 Claude Code 中输入以下命令测试：

```
使用深蓝堡垒团队审查这段代码
```

或：

```
/deepblue-bastion-coordinator
```

如果看到专家团队被触发，说明安装成功。

## 卸载

```bash
# 删除 Agent 配置
rm ~/.claude/agents/deepblue-bastion-*.md

# 删除 Skill 配置
rm -rf ~/.claude/skills/deepblue-bastion-coordinator
```

## 常见问题

### Q: 触发词不生效？

检查：
1. 文件是否在正确位置
2. 文件名是否正确（注意大小写）
3. 是否已重启 Claude Code

### Q: 专家没有被触发？

协调器会根据任务类型自动选择专家。可以明确指定：

```
使用 Aegis 进行安全审计
```

### Q: 如何自定义专家行为？

编辑对应的 `.md` 文件，修改专家的职责描述或触发词。
