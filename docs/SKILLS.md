# 云舒数字灵魂计划 - 技能系统文档

> **版本**: v2.4

---

## 一、技能概述

云舒系统采用**技能驱动**架构，所有可复用的能力都被封装为独立的 Skill 模块。

### 1.1 技能设计原则

| 原则 | 说明 |
|:---|:---|
| **单一职责** | 每个技能只做一件事 |
| **可组合性** | 技能可以组合成工作流 |
| **自描述性** | SKILL.md 包含完整文档 |
| **可测试性** | 每个 skill 都有验证方法 |

### 1.2 技能目录结构

```
.trae/skills/{skill-name}/
├── SKILL.md           # 技能元数据与文档 (必须)
├── skill.yaml         # 技能配置 (可选)
├── main.py            # 入口脚本
├── core/              # 核心模块
│   ├── __init__.py
│   └── *.py
├── scripts/           # 辅助脚本
└── requirements.txt   # 依赖 (可选)
```

---

## 二、核心技能详解

### 2.1 Autonomous Agent (自主执行引擎)

**优先级**: 100
**触发词**: 云舒、开始、继续、自主执行、autonomous、蜂群

**核心能力**:
- 5场景决策树
- 3维度质量把关
- Skill自动发现
- Swarm蜂群编排
- 交付文档生成

**CLI 接口**:
```bash
# 初始化
python .trae/skills/autonomous-agent/agent.py init

# 任务解析
python .trae/skills/autonomous-agent/agent.py analyze "任务描述"

# 完整工作流
python .trae/skills/autonomous-agent/agent.py workflow "任务描述"

# 质量检查
python .trae/skills/autonomous-agent/agent.py quality --session <ID>

# 交付与记忆
python .trae/skills/autonomous-agent/agent.py delivery --session <ID>
python .trae/skills/autonomous-agent/agent.py save --session <ID>
```

---

### 2.2 Spiral Loop System (螺旋循环系统)

**优先级**: 55
**触发词**: 检查点、循环检测、螺旋、规范检查、checkpoint

**核心能力**:
- Memory: 三层记忆结构
- Checkpoint: 状态快照与恢复
- Solver: 循环检测与螺旋跳跃
- Specs: 项目规范检查

**CLI 接口**:
```bash
# 记忆管理
python .trae/skills/spiral-loop-system/scripts/main.py memory --action add --content "内容"

# 检查点管理
python .trae/skills/spiral-loop-system/scripts/main.py checkpoint --action create --desc "描述"
python .trae/skills/spiral-loop-system/scripts/main.py checkpoint --action restore --id "ckpt_xxx"

# 循环求解
python .trae/skills/spiral-loop-system/scripts/main.py solver --action detect --state "状态"
python .trae/skills/spiral-loop-system/scripts/main.py solver --action jump --state "困境" --strategy spiral

# 规范检查
python .trae/skills/spiral-loop-system/scripts/main.py specs --action check_doc --file "path"
```

---

### 2.3 Quality Gate (质量门禁)

**优先级**: 70
**触发词**: 质量检查、质量把关、lint、quality gate

**检查维度**:
1. 边界处理检查
2. 专业度检查
3. 完整性检查
4. 真实验证

**CLI 接口**:
```bash
python .trae/skills/quality-gate/main.py "path/to/file_or_dir"
```

---

### 2.4 Task Decomposer (任务拆解器)

**优先级**: 65
**触发词**: 任务拆解、拆分任务、分解任务、task decompose

**核心能力**:
- 原子级任务拆解
- 执行计划生成
- 依赖关系分析
- 知识边界感知

**CLI 接口**:
```bash
python .trae/skills/task-decomposer/main.py "任务描述"
```

**输出格式**:
```json
{
  "session_id": "xxx",
  "total_tasks": 5,
  "execution_order": ["task1", "task2", ...],
  "tasks": [...]
}
```

---

### 2.5 Agent Skill Creator (技能创造器)

**优先级**: 45
**触发词**: 创建技能、做一个技能、开发工具

**创建流程**:
```
PHASE 1: DISCOVERY (发现)
├─ 分析需求
├─ 技术选型
└─ 可行性验证

PHASE 2: DESIGN (设计)
├─ 交互模式
├─ 输入输出
└─ 错误处理

PHASE 3: ARCHITECTURE (架构)
├─ 目录结构
└─ 文件布局

PHASE 4: IMPLEMENTATION (实现)
├─ 编写代码
└─ 编写 SKILL.md

PHASE 5: VALIDATION (验证)
├─ 安装依赖
├─ 功能测试
└─ 交付确认
```

---

### 2.6 Feishu Doc Master (飞书文档大师)

**优先级**: 50
**触发词**: 飞书、云文档、群话题、PRD文档、知识库文档

**核心能力**:
- 费曼学习法深度集成
- 飞书格式美学优化
- 难易度一致性校准
- 移动端阅读适配

**费曼四步法**:
```
Step 1: 选择概念 -> 识别核心概念
Step 2: 教给孩子 -> 创建通俗解释
Step 3: 识别漏洞 -> 检查卡顿点
Step 4: 简化重组 -> 优化输出
```

---

### 2.7 Neuro Bridge (神经桥接)

**优先级**: 60
**触发词**: 键鼠模拟、截图分析、本地模型、neuro

**核心能力**:
1. 深度推理 (deep_reasoning)
2. 记忆管理 (manage_memory)
3. MCP 服务器管理
4. 代码搜索与理解
5. 文件修改与验证
6. 浏览器自动化

**工作流模板**:
- 需求到改动
- 问题定位与修复
- 批量改名/替换
- 网页信息提取
- 知识沉淀

---

### 2.8 Knowledge Distiller (知识蒸馏器)

**优先级**: 50
**触发词**: 学习、研究、蒸馏、费曼、通俗化

**工作流程**:
```
Stage 1: 搜索获取
├─ 多关键词搜索
├─ 多来源验证
└─ 收集原始素材

Stage 2: 整理归纳
├─ 去重去噪
├─ 分类整理
└─ 建立结构

Stage 3: 蒸馏提取
├─ 提取核心概念
├─ 识别关键关系
└─ 精炼知识精华

Stage 4: 费曼转化
├─ 简化表达
├─ 类比说明
└─ 通俗化输出
```

---

### 2.9 Delivery Documenter (交付文档生成)

**优先级**: 40
**触发词**: 交付文档、生成交付、delivery

**输出内容**:
1. 任务摘要与文件变更
2. 部署步骤
3. 验证方法
4. 限制说明
5. 后续建议

**CLI 接口**:
```bash
python .trae/skills/delivery-documenter/main.py "任务描述" --session-id "SESSION_ID"
```

---

### 2.10 Memory Node (记忆管理)

**核心功能**:
- 记忆写入
- 记忆读取
- 记忆发现

**CLI 接口**:
```bash
# 写入
python .trae/skills/memory-node/memory_manager.py write --topic "topic" --content "content"

# 读取
python .trae/skills/memory-node/memory_manager.py read --topic "topic"
```

---

## 三、技能开发规范

### 3.1 SKILL.md 格式

```markdown
---
name: skill-name
version: "1.0.0"
description: 技能描述
tags: ["tag1", "tag2"]
triggers:
  - 触发词1
  - 触发词2
priority: 50
---

# Skill Name

## Description
...

## Usage
...
```

### 3.2 代码规范

- 使用 `argparse` 处理命令行参数
- 包含完整的错误处理
- 遵循 Python PEP8 规范
- 单文件不超过 500 行

---

*云舒数字灵魂计划 - 技能系统文档*