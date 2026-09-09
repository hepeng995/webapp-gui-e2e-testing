> 用法：本模板**按批次或 L1 模块合并**到一个结果文件使用（如 `results/B1-权限-结果.md`、`results/ORD-订单-结果.md`），禁止每条用例单独建文件；跨用例统计一律以 `results/summary.json` 为准。

### TC-<编号> <标题>

- 状态：PASS / FAIL / FLAKY（不稳定，见 execution-loop §4.1）/ BLOCKED / SKIPPED（原因）/ INTERRUPTED（续跑点）
- 优先级：P0 / P1 / P2 / P3
- 被测对象：L1 <模块> → L2 <页面> → L3 <功能区> → L4 <元素>
- 预期与来源：<该对象的正确预期效果>（来源：文档 x §y / 依据代码 / 用户 <裁决日期>）
- 账号：<账号名（角色语义）>
- 环境：本地环境（:端口）或 网络测试环境（地址）
- 步骤摘要与断言结果：
  1. … → 断言通过/失败（差异说明）
  2. …
- 网络：<method path> → <status>（关键 body 字段与幂等键；无网络断言写"不适用"）
- 截图：screenshots/<用例编号>-<序号>-<语义>.png（…）
- 日志：logs/<用例编号>/console.log、network.md（无异常写"console 无 error/warning"）
- 缺陷：BUG-<前缀>NNN（FAIL 时必填）
- 失败四件套（FAIL/FLAKY 必填）：截图 <路径>｜日志 <logs 路径+关键报错摘要>｜复现步骤（或 BUG 单号）｜成功定位方式 <role/text/testid/坐标>
- 备注：与其他测试的依赖/协调事项
