# Web3 Go QA 工具包：参考资料归档

归档日期：2026-11-21。此目录与仓库原有 CEX Skills 分开管理。

## 保存了什么

- 9 个上游开源项目在锁定提交下的 README 与许可证，版本及源文件 SHA 见 repositories.lock.json。
- 本地已有 web3-qa-workflow、api-scenario-automation 的 Skill 参考快照，见 skill-references/snapshots/。
- 仓库原有 9 个 CEX 业务 Skill 继续放在原目录，本目录只建立索引。

这是资料与来源快照，不是完整 fork，也不代表所有工具已安装、集成或验证。实际运行依赖以首版工具包的 go.mod/go.sum 为准。未确认的业务规则须评审，不能把生成建议当作生产规则。

## 首版：同用户资金账户与现货账户内部划转

四项交付：业务状态准备器、公共 Go 验证 SDK、CI 质量检查器、失败证据包。使用本地合成用户、TESTUSD 测试资产和隔离 MySQL，不连接真实交易所或真实资金。

| 上游项目 | 首版用途 | 阶段 |
|---|---|---|
| [go-testfixtures/testfixtures](https://github.com/go-testfixtures/testfixtures) | 隔离测试库数据夹具；会清理已有数据 | optional |
| [foundry-rs/foundry](https://github.com/foundry-rs/foundry) | Anvil本地链与合约专项 | later |
| [jaegertracing/jaeger](https://github.com/jaegertracing/jaeger) | 调用链排查 | later |
| [microcks/microcks](https://github.com/microcks/microcks) | API Mock与契约平台参考 | reference |
| [testcontainers/testcontainers-go](https://github.com/testcontainers/testcontainers-go) | 准备隔离的真实测试依赖 | core |
| [uber-go/mock](https://github.com/uber-go/mock) | Go接口级单元测试Mock | optional |
| [Shopify/toxiproxy](https://github.com/Shopify/toxiproxy) | 网络故障增强 | later |
| [gotestyourself/gotestsum](https://github.com/gotestyourself/gotestsum) | Go测试执行、JSON与JUnit报告 | core |
| [k1LoW/runn](https://github.com/k1LoW/runn) | 场景编排参考，不与Go主线重复维护 | reference |

core：首版选用；optional：按需要选用；reference：设计参考；later：后续阶段。首版不会为了使用开源项目而引入完整平台。

## Skill 使用边界

见 [skill-references/README.md](skill-references/README.md)。Skill 辅助需求分析、覆盖检查、评审和产物组织；Go 工具包的执行与判定不依赖在线模型。上游 README 和代码中的命令属于归档资料，不会自动执行。

## 扩展顺序

1. 资金内部划转：事务、幂等、并发与账实一致。
2. 网络故障、异步事件与排障证据增强。
3. 现货冻结、成交、撤单、手续费和流水。
4. 合约仓位、保证金、reduce-only；资金费与强平单独扩展。
5. Anvil 本地链的充提、事件和回执；DEX 报价、授权、Swap、滑点与余额。
6. 按需将执行结果接入 Leon QA；不作为首版前置依赖。

## 许可与来源

各 upstreams 子目录保留上游许可证与署名，快照并不改变原许可证。Foundry 同时保存 Apache 与 MIT 两份许可文件。Skill 快照属于本账号已有本地工作资料，历史本机路径保留在快照里，仅供参考，迁移时需要调整。
