# 无限画布 Codex 插件

让 Codex 打开并操作无限画布（https://img.aizzz.vip）。

## 准备

- 已安装并登录 Codex（桌面版或命令行都可以）
- 已安装 Node.js 18 或更高版本

## 安装

```bash
codex plugin marketplace add aizzzvip/canvas-plugin
codex plugin add aizzz-canvas@aizzzvip
```

## 使用

新建一个 Codex 任务，输入：

```text
打开无限画布
```

Codex 会启动本地 Canvas Agent，在右侧打开无限画布并自动连接。之后可以直接让 Codex 读取画布、创建节点、生成图片或视频。

生成图片和视频使用的是你在无限画布里配置的渠道和 API Key。

## 更新

```bash
codex plugin marketplace upgrade aizzzvip
codex plugin add aizzz-canvas@aizzzvip
```

## 卸载

```bash
codex plugin remove aizzz-canvas@aizzzvip
```
