# Skill 参考索引

## 业务规则与评审

复用仓库原有目录（不覆盖、不搬迁）：

- [cex-business-modeling](../../cex-business-modeling/)：按实际需求选择，资金首版重点关注需求评审、资金对账、测试点及用例评审。
- [cex-change-regression](../../cex-change-regression/)：按实际需求选择，资金首版重点关注需求评审、资金对账、测试点及用例评审。
- [cex-funds-reconciliation](../../cex-funds-reconciliation/)：按实际需求选择，资金首版重点关注需求评审、资金对账、测试点及用例评审。
- [cex-futures-risk](../../cex-futures-risk/)：按实际需求选择，资金首版重点关注需求评审、资金对账、测试点及用例评审。
- [cex-requirement-review](../../cex-requirement-review/)：按实际需求选择，资金首版重点关注需求评审、资金对账、测试点及用例评审。
- [cex-spot-matching](../../cex-spot-matching/)：按实际需求选择，资金首版重点关注需求评审、资金对账、测试点及用例评审。
- [cex-testcase-design-review](../../cex-testcase-design-review/)：按实际需求选择，资金首版重点关注需求评审、资金对账、测试点及用例评审。
- [cex-testpoint-design](../../cex-testpoint-design/)：按实际需求选择，资金首版重点关注需求评审、资金对账、测试点及用例评审。
- [cex-testpoint-review](../../cex-testpoint-review/)：按实际需求选择，资金首版重点关注需求评审、资金对账、测试点及用例评审。

## 工作流快照

- snapshots/web3-qa-workflow/：CEX/DEX 测试产物组织与证据登记参考。
- snapshots/api-scenario-automation/：接口清单、场景依赖、数据提取与断言格式参考。

快照包含历史“小测 Web3 测试台”路径及说明，不代表当前新工具包已接入该平台；不应直接照搬本机路径。快照仅保存明确的 Skill 包文件，不包含账号、密钥或运行配置。Go 首版使用原生 Go testing 与真实 MySQL 验证事务和并发，不强行转成 Python 接口编排。
