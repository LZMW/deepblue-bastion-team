# DeepBlue Bastion 团队安装指南

---

## 安装位置

本团队配置需要安装到以下位置：

| 组件类型 | 安装位置 |
|----------|----------|
| 协调器 Skill | `C:\Users\Mr.Chen\.claude\skills\deepblue-bastion-coordinator\` |
| 专家 Agents | `C:\Users\Mr.Chen\.claude\agents\` |

---

## 安装步骤

### 步骤1：创建目录

```powershell
# 创建协调器目录
mkdir -Force "C:\Users\Mr.Chen\.claude\skills\deepblue-bastion-coordinator"

# 确认agents目录存在
mkdir -Force "C:\Users\Mr.Chen\.claude\agents"
```

### 步骤2：复制协调器 Skill

```powershell
# 复制协调器skill.md
Copy-Item "N:\编程备份\4.0团队\deepblue-bastion-team\skills\deepblue-bastion-coordinator\skill.md" -Destination "C:\Users\Mr.Chen\.claude\skills\deepblue-bastion-coordinator\skill.md"
```

### 步骤3：复制专家 Agents

```powershell
# 复制所有专家配置
Copy-Item "N:\编程备份\4.0团队\deepblue-bastion-team\agents\*.md" -Destination "C:\Users\Mr.Chen\.claude\agents\"
```

### 步骤4：验证安装

```powershell
# 验证协调器
Get-Content "C:\Users\Mr.Chen\.claude\skills\deepblue-bastion-coordinator\skill.md" | Select-Object -First 5

# 验证专家
Get-ChildItem "C:\Users\Mr.Chen\.claude\agents\deepblue-bastion-*.md" | Select-Object Name
```

---

## 验证清单

安装完成后，请确认以下文件存在：

### 协调器
- [ ] `C:\Users\Mr.Chen\.claude\skills\deepblue-bastion-coordinator\skill.md`

### 专家（6个）
- [ ] `C:\Users\Mr.Chen\.claude\agents\deepblue-bastion-atlas.md`
- [ ] `C:\Users\Mr.Chen\.claude\agents\deepblue-bastion-aegis.md`
- [ ] `C:\Users\Mr.Chen\.claude\agents\deepblue-bastion-ockham.md`
- [ ] `C:\Users\Mr.Chen\.claude\agents\deepblue-bastion-bughunter.md`
- [ ] `C:\Users\Mr.Chen\.claude\agents\deepblue-bastion-turbo.md`
- [ ] `C:\Users\Mr.Chen\.claude\agents\deepblue-bastion-pragmatic.md`

---

## 使用方法

安装完成后，重启 Claude Code，然后使用以下命令触发团队：

```
/deepblue-bastion-coordinator
```

---

## 一键安装命令

```powershell
# 创建目录
mkdir -Force "C:\Users\Mr.Chen\.claude\skills\deepblue-bastion-coordinator"
mkdir -Force "C:\Users\Mr.Chen\.claude\agents"

# 复制协调器
Copy-Item "N:\编程备份\4.0团队\deepblue-bastion-team\skills\deepblue-bastion-coordinator\skill.md" -Destination "C:\Users\Mr.Chen\.claude\skills\deepblue-bastion-coordinator\skill.md" -Force

# 复制专家
Copy-Item "N:\编程备份\4.0团队\deepblue-bastion-team\agents\*.md" -Destination "C:\Users\Mr.Chen\.claude\agents\" -Force

Write-Host "安装完成！" -ForegroundColor Green
```

---

## 卸载

如需卸载，删除以下文件：

```powershell
# 删除协调器
Remove-Item "C:\Users\Mr.Chen\.claude\skills\deepblue-bastion-coordinator" -Recurse -Force

# 删除专家
Remove-Item "C:\Users\Mr.Chen\.claude\agents\deepblue-bastion-*.md" -Force
```

---

## 版本信息

- **版本**：4.0
- **生成日期**：2026-03-02
