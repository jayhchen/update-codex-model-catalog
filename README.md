# update-codex-model-catalog

更新 Codex 模型目录的 agent skill。

Codex 在 API key 鉴权模式下不会自动刷新模型目录，服务端模型增删后需手动同步——本 skill 完成这件事。

## 安装

```bash
# 仅安装到 Codex
npx skills add jayhchen/update-codex-model-catalog -a codex

# 仅安装到 Claude Code
npx skills add jayhchen/update-codex-model-catalog -a claude-code

# 自动探测本机已安装的 agent
npx skills add jayhchen/update-codex-model-catalog
```

## 使用

对 agent 说「更新 codex 模型目录」即可触发。流程：检查鉴权 → 拉取并校验目录 → 备份替换 → 报告增删变化。

安全设计：key 只在命令内直传、不回显，写前自动备份，校验失败不落盘。

## License

[MIT](LICENSE)
