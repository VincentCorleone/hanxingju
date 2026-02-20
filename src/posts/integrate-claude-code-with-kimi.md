---
date: 2026-02-20
category:
  - Tech
tag:
  - AI
---
# Claude Code 集成 Kimi 模型完全指南

> **亲测有效**：通过配置环境变量，让 Claude Code 无缝使用 Kimi-K2.5 或 Kimi-for-Coding 模型

## 为什么要集成 Kimi？

Kimi 模型（尤其是 Kimi-K2.5 和 Kimi-for-Coding）在代码理解、生成和调试方面表现出色，具有几点优势：

- **便宜**

通过将 Claude Code 与 Kimi 集成，你可以获得更强大的代码辅助工具。

## 配置步骤

### 1. 准备工作

首先，确保你已经安装了 Claude Code 命令行工具。如果还没有安装，可以通过以下方式获取：

```bash
# 安装 Claude Code 工具
npm install -g @anthropic-ai/claude-code
```
### 2. 获取 Kimi API 密钥

1. 访问 [Kimi Code控制台](https://www.kimi.com/code/console)
2. 注册并登录账户
3. 创建并复制你的 API 密钥

### 3. 配置环境变量

**重要**：使用 `ANTHROPIC_AUTH_TOKEN` 而非 `ANTHROPIC_API_KEY`，这是与 Kimi 集成的关键区别。

#### Windows 系统

1. 右键点击「此电脑」→「属性」→「高级系统设置」→「环境变量」
2. 在「系统变量」中点击「新建」，添加以下两个环境变量：

| 变量名 | 变量值 |
|--------|--------|
| ANTHROPIC_BASE_URL | https://api.kimi.com/coding |
| ANTHROPIC_AUTH_TOKEN | 你的 Kimi API 密钥 |

#### macOS/Linux 系统

编辑你的 shell 配置文件（如 `~/.bashrc`、`~/.zshrc` 或 `~/.profile`）：

```bash
# 添加到 shell 配置文件
export ANTHROPIC_BASE_URL="https://api.kimi.com/coding"
export ANTHROPIC_AUTH_TOKEN="你的 Kimi API 密钥"

# 保存后生效
source ~/.bashrc  # 或相应的配置文件
```



## 使用方法

### 基本使用

配置完成后，你可以通过以下命令使用 Kimi-for-Coding 模型：


```bash
# 启动交互式会话
claude --model kimi-for-coding 
```


## 总结

通过简单配置 `ANTHROPIC_BASE_URL` 和 `ANTHROPIC_AUTH_TOKEN` 环境变量，你可以轻松将 Claude Code 与 Kimi 模型集成，获得更强大的代码辅助工具。


---

**温馨提示**：API 密钥属于敏感信息，请妥善保管，不要在公共代码库或分享平台中暴露。

**更新时间**：2026-02-20
**测试环境**：Windows 10 + Claude Code + Kimi-for-Coding