# Simulink Test 学习路线图（R2024b 官方文档）

> 状态图例：⬜ 未开始 · 🔄 学习中 · ✅ 已完成
> 每章笔记在 `notes/chNN-*.md`，官方链接在 [references.md](references.md)。
> 建议顺序：阶段 1 → 2 → 3 → 4，其余按需。带 ⭐ 的为"单元/回归测试"与"汽车功能安全"主线重点。

## 阶段 0：准备
- [ ] 0.1 环境与许可证清单（`ver` 检查产品、APPS 页找 Simulink Test）
- [ ] 0.2 文档导航与 `openExample` 打开官方示例的方法

## 阶段 1：快速入门与核心概念（对应官方"快速入门"）
- [ ] 1.1 ⭐ Simulink Test 全景：解决什么问题、典型测试工作流
- [ ] 1.2 ⭐ 核心对象与术语：Test File / Test Suite / Test Case / Iteration
- [ ] 1.3 ⭐ 三种测试类型：仿真测试 / 基线测试 / 等效性测试
- [ ] 1.4 ⭐ 动手：创建简单基线测试（官方教程 gs/create-a-simple-baseline-test）
- [ ] 1.5 测试计划与策略（gs/plan-your-test）

## 阶段 2：测试框架 Test Harness —— 单元测试的基石（官方"测试框架"）
- [ ] 2.1 ⭐ harness 与模型的关系：组件级/顶层、内部/外部存储、工作区与配置集
- [ ] 2.2 ⭐ 创建 harness：向导、源/汇选项、SIL/PIL harness
- [ ] 2.3 管理 harness：打开/关闭/转换/删除/导出
- [ ] 2.4 同步模型与 harness 的更改（push / rebuild / 同步选项）
- [ ] 2.5 特殊元素 harness：库模块、Model Reference、C Caller/S-Function、Stateflow
- [ ] 2.6 自定义 harness：回调、可复用函数、从独立模型导入

## 阶段 3：测试编写（官方"测试编写"）
- [ ] 3.1 ⭐ 测试用例与迭代：属性设置、同步测试、参数覆盖、仿真模式覆盖、故障注入
- [ ] 3.2 ⭐ 测试输入：外部数据（Excel/MAT/m 脚本）、Signal Editor、Design Verifier 自动生成
- [ ] 3.3 ⭐ 输出与信号记录：记录信号、捕获/更新基线数据
- [ ] 3.4 ⭐ Test Sequence 模块：步骤/转移/时序运算符/场景/外部函数
- [ ] 3.5 ⭐ Test Assessment 与验证：verify/assert、When 分解、逻辑与时序评估
- [ ] 3.6 Observer：无线访问模型数据（信号、消息、状态、FMU 变量）
- [ ] 3.7 容差设置：值容差（相对/绝对）与时间容差（超前/滞后）

## 阶段 4：测试执行（官方"测试执行"）
- [ ] 4.1 ⭐ 执行模式与并行执行；迭代、标签、测试筛选
- [ ] 4.2 ⭐ 基线测试 / 等效性（背靠背）测试 / 多版本测试
- [ ] 4.3 ⭐ SIL / PIL / HIL 测试与生成代码测试
- [ ] 4.4 解释测试结果、调试测试（模型切片器、仿真数据检查器）
- [ ] 4.5 ⭐ 测试覆盖率：Simulink Coverage 指标、Design Verifier 增补用例、覆盖率过滤

## 阶段 5：结果、报告与测试文件管理（官方"结果、报告和测试文件管理"）
- [ ] 5.1 导出测试结果、生成/自定义测试结果报告
- [ ] 5.2 测试规范报告（生成与自定义）
- [ ] 5.3 测试文件管理：依赖管理、比较与合并测试文件

## 阶段 6：自动化与持续集成（官方"测试脚本"+"持续集成"）
- [ ] 6.1 ⭐ 编程接口：sltest.testmanager（TestFile/TestSuite/TestCase）、sltest.harness、sltest.testsequence
- [ ] 6.2 ⭐ 基于 MATLAB 的 Simulink 测试：sltest.TestCase + matlab.unittest 框架
- [ ] 6.3 CI 集成：Jenkins 等 CI 系统的结果/覆盖率输出、并行与批处理

## 阶段 7：需求追溯与行业标准
- [ ] 7.1 ⭐ 需求链接与基于需求的测试（Requirements Toolbox）：可追溯性、需求覆盖率
- [ ] 7.2 ⭐ 功能安全：ISO 26262 / IEC 61508 下的测试实践（V 模型、单元/集成验证）
- [ ] 7.3 工具鉴定与认证：IEC Certification Kit / DO Qualification Kit（DO-178）

---

## 进度总览

| 阶段 | 章节数 | 已完成 | 状态 |
|------|-------|-------|------|
| 0 准备 | 2 | 0 | ⬜ |
| 1 快速入门 | 5 | 0 | ⬜ |
| 2 测试框架 | 6 | 0 | ⬜ |
| 3 测试编写 | 7 | 0 | ⬜ |
| 4 测试执行 | 5 | 0 | ⬜ |
| 5 结果与报告 | 3 | 0 | ⬜ |
| 6 自动化与 CI | 3 | 0 | ⬜ |
| 7 标准与认证 | 3 | 0 | ⬜ |
