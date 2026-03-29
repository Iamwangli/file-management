---
name: file-management
description: 文件管理规范skill，定义项目命名和组织的标准
---

# file-management

文件管理规范skill，定义项目命名和组织的标准。

## 目的
将文档管理公约转化为可执行的规范，确保项目命名和组织的一致性。

## 核心原则
1. **方便再次使用**：命名直观、分类清晰、流程顺畅
2. **项目隔离**：每个项目在独立文件夹内工作
3. **命名规范**：小写字母、连字符分隔、描述性强
4. **扩展前缀**：新类型添加到前缀表

## 规范

### 开发流程
```
workspace开发 → Documents归档
```

### 命名规则
- 小写字母
- 连字符分隔单词
- 避免特殊字符、空格、下划线

### 前缀系统
| 类型 | 前缀 | 示例 |
|------|------|------|
| Python | `py-` | `py-data-processor` |
| Web | `web-` | `web-dashboard` |
| 工具 | `tool-` | `tool-backup` |
| OpenClaw技能 | `ocw-` | `ocw-file-management` |
| FPGA/RTL | `rtl-` | `rtl-riscv-multiplier` |
| 文档 | `doc-` | `doc-api-reference` |
| JavaScript | `js-` | `js-chart-library` |
| 配置 | `config-` | `config-server-setup` |
| 测试 | `test-` | `test-performance` |
| 学习 | `learn-` | `learn-rust-basics` |
| 安全审计 | `audit-` | `audit-skill-security` |
| 数据分析 | `data-` | `data-analysis` |
| 自动化 | `auto-` | `auto-deploy` |

### 项目结构
```
项目名称/
├── src/
├── tests/
├── docs/
├── scripts/
├── README.md
└── .gitignore
```

## 参考

### 创建项目
```bash
mkdir ~/.openclaw/workspace/py-my-app
cd ~/.openclaw/workspace/py-my-app
mkdir -p src tests docs scripts
touch README.md .gitignore
```

### 检查命名
```bash
# 检查问题
find . -type f -name "*[A-Z]*" -o -name "*_*" -o -name "* *"

# 修复问题
for f in *; do mv "$f" "$(echo $f | tr 'A-Z _' 'a-z--')"; done
```

### 归档项目
```bash
mv ~/.openclaw/workspace/py-my-app ~/Documents/py-my-app
```

## 版本
- 版本: 1.1.0
- 创建: 2026-03-29
- 更新: 2026-03-29 (添加audit-等前缀)
