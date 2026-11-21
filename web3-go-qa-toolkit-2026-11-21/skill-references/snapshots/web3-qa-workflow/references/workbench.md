# 小测工作台接入

本地工作台目录为 `/Users/Admin1/Documents/ChatGPT/web3工作/output/xiaoce-web3-workbench`，入口 `http://127.0.0.1:8831/`。若该安装目录被迁移，在用户当前工作区定位 workbench.py 和 runs/。服务未启动时，用 `python3 workbench.py serve` 启动。无需发布或访问外部网站。可用 Codex 的右侧浏览器打开该地址。

从工作台目录调用：

```bash
python3 workbench.py init <batch-id> --title '<测试主题>' --environment '<测试环境>' --version '<提测版本或需求单号>'
python3 workbench.py stage <batch-id> scope working
python3 workbench.py stage <batch-id> scope ready scope.md --note '<范围摘要>'
python3 workbench.py stage <batch-id> coverage review coverage.json --note '<待确认和覆盖摘要>'
```

把脱敏产物写在该批次的 `runs/<batch-id>/` 下，命令中的文件名相对于这个批次。不要随意改用户已有的批次，复用时先核对版本、环境与既有结果。阶段名和建议文件：

| 阶段参数 | 产物 |
| --- | --- |
| scope | scope.md，脱敏需求和接口契约 |
| coverage | coverage.json，待确认规则、范围及风险抽取 |
| cases | cases.json / cases.md、XMind、需求到用例关联 |
| data | data-plan.md、fixture、页面准备数据的截图与生成的测试数据 ID |
| plan | run-plan.md、场景文件、脚本、Collection 或测试计划 |
| evidence | junit.xml 或团队脱敏报告、缺陷与复测记录 |

状态为 `todo`、`working`、`review`、`ready`、`blocked`、`failed`。只有确实有产物才标已就绪。执行前登记编排并核对目标，执行中可即时记录 working。失败/阻塞记录原因，复测与原报告用不同文件。每完成或阻塞一个阶段便登记，同一页面会自动刷新。网页仅展示登记后的文件与结果。

coverage.json 是 JSON 数组。每行包含 `id, domain, scenario, oracle, priority, status, caseId`。可附加 `requirement, source, openQuestion`。状态用 `verified`、`review`、`todo`。核验到本批 JUnit 的匹配用例确实通过时才用 verified。未运行或非 JUnit 证据写待验证并在报告说明。工作台会交叉核对当前批次、阶段更新时间和 JUnit 结果。pytest 命名形如 `test_tc_spot_cancel_001_partial_cancel` 可显示为 TC_SPOT_CANCEL_001。其他命名使用 JUnit testcase 的 name 值。
