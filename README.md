# webapp-gui-e2e-testing（Web GUI E2E 测试通用 Skill）

用 Agent 内置浏览器（当前 Agent 工具自带，如 ZCode）对任意 Web 应用做黑盒 GUI/E2E/验收/回归/探索性测试，产出带证据的测试报告。版本与变更记录以 SKILL.md §9 为准。

## 安装

方式一（推荐，从 GitHub 克隆）：克隆到所用 Agent 工具的用户级 skills 目录——

```bash
git clone https://github.com/hepeng995/webapp-gui-e2e-testing.git <skills目录>/webapp-gui-e2e-testing
```

skills 目录按所用工具的约定，例如：ZCode 为 `~/.zcode/skills/`、Claude Code 为 `~/.claude/skills/`（Windows 下 `~` 即 `%USERPROFILE%`）。

方式二（手动复制）：下载 [main.zip](https://github.com/hepeng995/webapp-gui-e2e-testing/archive/refs/heads/main.zip) 解压，把 `webapp-gui-e2e-testing` 文件夹整体放入所用工具的 skills 目录。

安装后重开 Agent 会话生效。共 19 个文件（SKILL.md + README + 10 份 references + 7 份模板）；要求运行环境具备内置浏览器能力，测试产出默认中文。

## 使用

- 自动触发：直接描述测试任务（"测一下 http://localhost:5173 的登录和建单流程，出带截图的报告"）；
- 显式触发：按所用 Agent 工具的 skill 调用方式（如斜杠命令 `/webapp-gui-e2e-testing <任务描述>`）；
- 你需要提供：被测地址、账号及密码来源；可选：用例清单、数据前缀、产出目录。只给 URL 也可以，skill 会自动走"代码+文档→生成用例文档→摘要展示（非阻塞）→执行"的完整流程。

## 结构

```
SKILL.md                 # 总纲：流程、证据三件套、黑盒/灰盒/白盒口径、硬约束
references/              # 10 份细则：生成/规划/覆盖维度/执行循环/证据/问题/环境/工具边界/多Agent/产物沉淀
assets/templates/        # 7 份产出模板（含 summary.json 示例）
```

## 说明

- 本 skill 为**通用版**，任意 Web 项目可复用；测试证据与报告全部落在用户指定的产出目录（缺省 `./e2e-results/`），结构见 `references/artifacts-handoff.md` §0。
- **全程中文**：与用户的沟通及全部产出文档（报告/BUG 单/用例文档等）使用中文；技术标识（用例编号、状态码、命令、代码、URL）保留英文原样。
