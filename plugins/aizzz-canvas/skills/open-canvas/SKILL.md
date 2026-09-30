---
name: open-canvas
description: 打开无限画布并自动连接本地 Canvas Agent。用户要求打开、启动、进入或使用无限画布时使用。
---

# 打开无限画布

1. 启动本地 Canvas Agent 并保持运行：

```bash
npx -y https://img.aizzz.vip/agent/canvas-agent-0.7.1.tgz
```

2. 从启动输出取得 `Local URL` 和 `Connect token`。

3. 在 Codex 右侧浏览器打开：

```text
https://img.aizzz.vip/canvas?mode=new#agentUrl=<Local URL>&agentToken=<Connect token>
```

## 注意

- 只打开 `https://img.aizzz.vip`，不要打开其它画布网站。
- Canvas Agent 只使用上面这个无限画布提供的地址，它与网页的连接协议一致，不要改用 npm 上的其它包或版本。

## MCP 与连接地址

插件在新的 Codex 任务中加载时会自动启动 `npx -y https://img.aizzz.vip/agent/canvas-agent-0.7.1.tgz mcp`。这个 MCP 进程负责提供画布工具，不提供网页连接服务；
上面启动的普通 Canvas Agent 负责提供 `Local URL` 和 `Connect token`。两个进程读取同一份本地配置，因此不需要用户手动填写地址或 token。

## 打开模式

用户没有明确指定打开方式时，始终使用 `mode=new` 新建画布。只有用户明确要求时才替换为：

- 最近画布：`mode=recent`
- 自己选择：`mode=choose`
