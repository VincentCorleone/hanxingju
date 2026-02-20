---
date: 2026-02-20
category:
  - Tech
tag:
  - AI
---
# Complete Guide to Integrating Claude Code with Kimi Model

> **Tested and Verified**: Configure environment variables to seamlessly use Kimi-K2.5 or Kimi-for-Coding models with Claude Code

## Why Integrate Kimi?

Kimi models (especially Kimi-K2.5 and Kimi-for-Coding) excel in code understanding, generation, and debugging, with several advantages:

- **Affordable**

By integrating Claude Code with Kimi, you can get a more powerful code assistance tool.

## Configuration Steps

### 1. Prerequisites

First, make sure you have installed the Claude Code command-line tool. If not, you can get it via:

```bash
# Install Claude Code tool
npm install -g @anthropic-ai/claude-code
```
### 2. Get Kimi API Key

1. Visit [Kimi Code Console](https://www.kimi.com/code/console)
2. Register and log in to your account
3. Create and copy your API key

### 3. Configure Environment Variables

**Important**: Use `ANTHROPIC_AUTH_TOKEN` instead of `ANTHROPIC_API_KEY`, this is the key difference for Kimi integration.

#### Windows System

1. Right-click "This PC" → "Properties" → "Advanced system settings" → "Environment Variables"
2. Click "New" in "System variables" and add the following two environment variables:

| Variable Name | Variable Value |
|---------------|----------------|
| ANTHROPIC_BASE_URL | https://api.kimi.com/coding |
| ANTHROPIC_AUTH_TOKEN | Your Kimi API key |

#### macOS/Linux System

Edit your shell configuration file (such as `~/.bashrc`, `~/.zshrc`, or `~/.profile`):

```bash
# Add to shell configuration file
export ANTHROPIC_BASE_URL="https://api.kimi.com/coding"
export ANTHROPIC_AUTH_TOKEN="Your Kimi API key"

# Apply changes after saving
source ~/.bashrc  # or the corresponding configuration file
```



## Usage

### Basic Usage

After configuration, you can use the Kimi-for-Coding model with the following command:


```bash
# Start interactive session
claude --model kimi-for-coding 
```


## Summary

By simply configuring `ANTHROPIC_BASE_URL` and `ANTHROPIC_AUTH_TOKEN` environment variables, you can easily integrate Claude Code with Kimi models for a more powerful code assistance tool.


---

**Note**: API keys are sensitive information, please keep them secure and do not expose them in public code repositories or sharing platforms.

**Last Updated**: 2026-02-20
**Test Environment**: Windows 10 + Claude Code + Kimi-for-Coding
