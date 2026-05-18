# 客户端集成

## 默认本地网关

```text
OpenAI Responses 基础地址: http://127.0.0.1:50124/v1
Anthropic Messages 基础地址: http://127.0.0.1:50124
API 密钥: sk-tabbit-local
模型名: tabbit/priority
```

开始前先启动本地网关：

```powershell
tabbit2api start
```

如果你还没有 runtime profile，直接运行 `tabbit2api` 也可以，它会自动拉起登录并等待完成。

## Codex 接入

示例文件：

- [../examples/codex/config.toml.example](../examples/codex/config.toml.example)

Codex 使用 OpenAI Responses 兼容接口：

```text
基础地址: http://127.0.0.1:50124/v1
API 密钥环境变量: TABBIT_API_KEY
模型名: tabbit/priority
```

## Claude Code 接入

示例文件：

- [../examples/claude-code/env.powershell.example](../examples/claude-code/env.powershell.example)
- [../examples/claude-code/env.sh.example](../examples/claude-code/env.sh.example)

Claude Code 使用 Anthropic 风格接口：

```text
基础地址: http://127.0.0.1:50124
API 密钥: sk-tabbit-local
模型名: tabbit/priority
```

注意：这里不要带 `/v1`。

## OpenClaw 接入

OpenClaw 也走 Anthropic 风格接口，因此同样使用：

```text
基础地址: http://127.0.0.1:50124
```

## Hermes Agent 接入

Hermes Agent 使用 OpenAI Responses 兼容接口：

```text
基础地址: http://127.0.0.1:50124/v1
API 模式: codex_responses
模型名: tabbit/priority
```

## 常见差异

- Codex / Hermes Agent：通常用 `/v1`
- Claude Code / OpenClaw：通常不用 `/v1`
- 所有客户端都建议统一用 `tabbit/priority`

## 首次接入建议

1. 运行 `tabbit2api doctor`
2. 运行 `tabbit2api start`
3. 访问 `/health`
4. 再接客户端配置
