# Kimi-guide

## 单独API Key账户

https://platform.kimi.com/console/pay

```
export ANTHROPIC_BASE_URL="https://api.moonshot.cn/anthropic"
export ANTHROPIC_AUTH_TOKEN="你的_Kimi_API_Key"

export ANTHROPIC_MODEL="kimi-k3[1m]"
export ANTHROPIC_DEFAULT_OPUS_MODEL="kimi-k3[1m]"
export ANTHROPIC_DEFAULT_SONNET_MODEL="kimi-k3[1m]"
export ANTHROPIC_DEFAULT_HAIKU_MODEL="kimi-k3[1m]"
export ANTHROPIC_DEFAULT_FABLE_MODEL="kimi-k3[1m]"
export CLAUDE_CODE_SUBAGENT_MODEL="kimi-k3[1m]"

export CLAUDE_CODE_AUTO_COMPACT_WINDOW="1048576"
export CLAUDE_CODE_EFFORT_LEVEL="max"

```

## 订阅账户

使用 WSL，则应在 WSL 终端使用 Linux 的 export 命令，而不是 PowerShell 命令：
```
export ANTHROPIC_BASE_URL="https://api.kimi.com/coding/"
export ANTHROPIC_API_KEY="你的_Kimi_Code_API_Key"
export ANTHROPIC_MODEL="kimi-for-coding"

export ANTHROPIC_DEFAULT_OPUS_MODEL="$ANTHROPIC_MODEL"
export ANTHROPIC_DEFAULT_SONNET_MODEL="$ANTHROPIC_MODEL"
export ANTHROPIC_DEFAULT_HAIKU_MODEL="$ANTHROPIC_MODEL"
export CLAUDE_CODE_SUBAGENT_MODEL="$ANTHROPIC_MODEL"

claude

```
## 另外的方法
```
export ANTHROPIC_BASE_URL="https://api.kimi.com/coding/"
export ANTHROPIC_API_KEY="你的_Kimi_Code_Key"

export ANTHROPIC_MODEL="kimi-for-coding"
export ANTHROPIC_DEFAULT_FABLE_MODEL="$ANTHROPIC_MODEL"
export ANTHROPIC_DEFAULT_OPUS_MODEL="$ANTHROPIC_MODEL"
export ANTHROPIC_DEFAULT_SONNET_MODEL="$ANTHROPIC_MODEL"
export ANTHROPIC_DEFAULT_HAIKU_MODEL="$ANTHROPIC_MODEL"
export CLAUDE_CODE_SUBAGENT_MODEL="$ANTHROPIC_MODEL"

export CLAUDE_CODE_EFFORT_LEVEL="high"
export CLAUDE_CODE_AUTO_COMPACT_WINDOW="262144"
export CLAUDE_CODE_MAX_CONTEXT_TOKENS="262144"

claude
```

## Truble

<img width="477" height="163" alt="image" src="https://github.com/user-attachments/assets/008dc291-2850-4ced-af95-8620ee0db07e" />

选第一项：**Kimi Code (OAuth)**，然后按 Enter。

这最适合你的情况，因为你要使用的是 **Kimi 订阅/Kimi Code 权益**，接下来浏览器登录 Kimi 账号即可，不需要填写 API Key。

下面两项用于按量付费 API：

* `platform.kimi.com`：国内 API 平台，人民币充值
* `platform.kimi.ai`：国际 API 平台，通常美元结算

登录完成后直接运行 `kimi`，而 Claude 模型继续单独使用 `claude`，两套配置不会互相干扰。


