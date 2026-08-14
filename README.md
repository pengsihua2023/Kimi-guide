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

## Truble 2

这是 OAuth 授权尚未完成。WSL 有时不会自动打开 Windows 浏览器。这样处理：

1. 按 `Ctrl+C` 取消等待，退出 Kimi 界面。
2. 在普通 WSL 终端运行：

```bash
kimi login
```

3. 终端会显示：

* 一个验证网址
* 一段授权码

把网址复制到 Windows 浏览器打开，登录你购买 Kimi 订阅的账号，然后输入授权码并确认。浏览器显示授权成功后，WSL 会自动完成登录。

如果没有显示网址和授权码，先更新：

```bash
kimi update
kimi login
```

成功时终端会结束 `Waiting for authorization`。然后运行：

```bash
kimi
```

输入简单问题测试，例如：

```text
1+1等于多少？
```

这种登录采用设备授权流程，不依赖 WSL 的浏览器回调；链接甚至可以在手机上打开。不要关闭正在运行 `kimi login` 的终端，直到网页授权完成。[Kimi Code 官方登录说明](https://www.kimi.com/code/docs/en/kimi-code-cli/reference/kimi-command.html)

## Truble 3
这说明命令运行正常，现在需要在浏览器完成授权：

1. 在 Windows 浏览器打开终端显示的授权网址。
2. 登录购买了 **Kimi/Kimi Code 订阅**的账号。
3. 点击“授权/确认登录”。
4. 保持当前 WSL 终端不要关闭。

网页显示授权成功后，终端通常几秒内会自动结束等待。随后运行：

```bash
kimi
```

如果浏览器没有自动打开，可以在 WSL 执行：

```bash
explorer.exe "https://www.kimi.com/code/authorize_device?user_code=5X74-SYWT"
```

如果网页已显示授权成功，但终端仍等待超过一分钟，按 `Ctrl+C`，重新运行：

```bash
kimi login
```

然后使用新生成的链接和授权码。授权码相当于临时凭证，以后不要把尚未过期的代码发出来。



