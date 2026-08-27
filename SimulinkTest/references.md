# 官方文档速查（R2024b，Simulink Test）

> 统一前缀：`https://ww2.mathworks.cn/help/releases/R2024b/sltest/`

## 顶层章节
| 章节 | 页面 |
|------|------|
| 文档首页 | `index.html` |
| 快速入门 | `getting-started-with-simulink-test.html` |
| 测试编写 | `test-authoring.html` |
| ├ 测试框架 | `test-harnesses.html` |
| ├ 测试用例和迭代 | `test-files.html` |
| ├ 输入 | `inputs.html` |
| ├ 输出 | `outputs-and-signal-logging.html` |
| └ 评估、准则和验证 | `test-sequences-and-assessments.html` |
| 测试执行 | `test-execution.html` |
| ├ 功能/基线/多版本/并行 | `functional-baseline-multirelease-and-parallel-tests.html` |
| ├ SIL、PIL、HIL | `sil-pil-and-hil-tests.html` |
| ├ ASAM XIL | `asam-xil-tests.html` |
| ├ 生成代码测试 | `generated-code-tests.html` |
| ├ 解释测试结果 | `interpret-test-results.html` |
| ├ 调试测试 | `debug-tests.html` |
| └ 检查测试覆盖率 | `check-test-coverage.html` |
| 结果、报告和文件管理 | `test-results.html` |
| 测试脚本（自动化 API） | `automation.html` |
| 持续集成 | `continuous-integration.html` |
| 工具鉴定与认证 | `tools-qualification-and-certification.html` |

## 关键教程/主题页
- 创建简单基线测试：`gs/create-a-simple-baseline-test.html`
- 创建并运行背靠背测试：`ug/create-and-run-a-back-to-back-test.html`
- 创建测试框架：`gs/create-a-test-harness.html`
- 测试框架与模型关系：`ug/relationship-between-harness-and-model-block-diagrams.html`
- 测试迭代：`ug/run-multiple-combinations-of-tests-using-iterations.html`
- 测试序列基础知识：`ug/introduction-to-test-sequences.html`
- 测试序列和评估语法：`ug/syntax-for-test-sequences-and-assessments.html`
- 评估仿真并比较输出数据：`ug/test-assessment-basics.html`
- 使用时序评估：`ug/temporal-assessments.html`
- 无线访问模型数据（Observer）：`ug/access-model-data-wirelessly-by-using-observers.html`
- 设置信号容差：`ug/apply-tolerances-to-test-criteria.html`
- 收集测试覆盖率：`ug/collect-model-coverage-in-tests.html`
- 生成测试结果报告：`ug/generate-test-results-reports.html`
- 使用脚本创建并运行测试用例：`ug/create-and-run-test-cases-with-scripts.html`
- 基于 MATLAB 的 Simulink 测试：`ug/test-models-using-matlab-based-simulink-tests.html`
- 使用 MATLAB 单元测试测试模型：`ug/run-test-files-using-matlab-unit-test.html`

## 核心模块
| 模块 | 页面 |
|------|------|
| Test Sequence | `ref/testsequence.html` |
| Test Assessment | `ref/testassessment.html` |
| Observer Reference / Port | `ref/observerreference.html` / `ref/observerport.html` |
| Simulink 测试管理器（App） | `ref/simulinktestmanager.html` |

## 核心语法运算符（Test Sequence / Assessment 内）
`verify`、`assert`、`et`、`t`、`after`、`before`、`duration`、
`hasChanged`、`hasChangedFrom`、`hasChangedTo`、`square`、`sawtooth`、
`triangle`、`ramp`、`heaviside`、`latch`
→ 页面 `ref/verify.html`、`ref/assert.html`、`ref/after.html`、`ref/duration.html` 等

## 核心编程 API（sltest 命名空间）
- 测试结构：`sltest.testmanager.TestFile` / `TestSuite` / `TestCase` / `load` / `run` / `view`
- 框架：`sltest.harness.create` / `open` / `close` / `find` / `convert` / `rebuild`
- 序列：`sltest.testsequence.newBlock` / `addStep` / `addTransition` / `addSymbol`
- 输入/输出：`sltest.testmanager.TestInput` / `BaselineCriteria` / `EquivalenceCriteria` / `LoggedSignal`
- 迭代：`sltestiteration`、`sltest.testmanager.TestIteration` / `ParameterSet` / `ParameterOverride`
- 结果：`sltest.testmanager.ResultSet` / `TestFileResult` / `TestCaseResult` / `TestIterationResult`
- 报告：`sltest.testmanager.report` / `TestResultReport` / `TestSpecReport`
- 观测器：`sltest.observer.observeElement` / `addObserverReference` / `addObserverPort`
- MATLAB 测试集成：`sltest.TestCase` / `sltest.harness.SimulationInput` / `sltest.plugins.*`

## 相关工具箱（配套使用）
- Simulink Coverage（覆盖率）、Simulink Design Verifier（自动生成输入/用例）
- Requirements Toolbox（需求追溯）、Simulink Fault Analyzer（故障注入）
- Embedded Coder（SIL/PIL 代码）、Simulink Real-Time（HIL）、Stateflow（Test Sequence 底层）
- MATLAB Test / matlab.unittest（CI 集成）
- IEC Certification Kit / DO Qualification Kit（认证）
