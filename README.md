# multi-wallet-manager

多钱包地址管理 Codex skill，整理自 multichain-balance-manager 的开发经验，用于指导 AI 开发、维护和排查多链钱包管理工具。

适用场景：批量地址导入与去重、EVM / Solana 余额查询、LP 仓位识别、本地网页、同链归集与撤 LP 流程审查。强调查询覆盖范围、整数精度、凭证隔离和交易防重复广播。

这是供 AI 使用的方法与检查指南，不是可独立运行的钱包软件，不自带实时数据、签名服务或经过审计的资金执行程序。协议支持范围取决于实际项目实现。

## 安装

在 Codex 中使用内置 skill-installer：

```text
$skill-installer 安装 https://github.com/316878750/multi-wallet-manager 的根目录 skill，安装名称为 multi-wallet-manager。
```

也可以下载本仓库，将包含 `SKILL.md`、`agents/`、`references/` 的目录命名为 `multi-wallet-manager`，放入个人 skills 目录（默认 `~/.codex/skills/`）。安装后在下一轮对话中使用。

## 使用

```text
$multi-wallet-manager 根据我的地址清单批量查询余额，标明失败项和查询覆盖范围。
```

```text
$multi-wallet-manager 帮我开发一个本地网页版多钱包管理工具，支持 Ethereum、BSC、Arbitrum、Base、Solana。
```

```text
$multi-wallet-manager 检查现有归集程序的手续费预留和重复转账风险。
```

说明链与网络、地址文件位置、查询或执行范围即可。只读查询只需要公开地址；请勿将私钥、助记词或接口凭证发送到聊天或提交到仓库。开发和查询请求不构成真实转账授权。

## 文件

- [SKILL.md](SKILL.md)：触发范围、工作流程与交付要求。
- [查询与覆盖](references/query-and-coverage.md)：地址校验、RPC、资产发现与 LP 覆盖。
- [归集与执行](references/execution.md)：规则授权、签名隔离、费用、恢复与验证。
- [Codex 显示信息](agents/openai.yaml)：名称和简介。
