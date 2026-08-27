# Simulink Test 学习项目

> 以 MathWorks 官方文档（R2024b）为教材，系统学习 Simulink Test™ 工具箱。
> 官方入口：https://ww2.mathworks.cn/help/releases/R2024b/sltest/index.html

## 学习目标

1. **系统掌握** Simulink Test 全部功能：测试编写、执行、结果管理、自动化、CI。
2. **重点方向**：
   - 单元测试与回归测试（Test Harness + 基线测试 + 自动化）
   - 汽车电子 / 功能安全（需求追溯、覆盖率、SIL/PIL、ISO 26262 支持）
3. **产出**：随学随写的结构化中文笔记（`notes/` 目录），每章附官方文档对应链接。

## 使用方法

- 学习路线图与进度跟踪见 [`ROADMAP.md`](ROADMAP.md)（每章完成后更新状态）。
- 官方文档关键页面速查见 [`references.md`](references.md)。
- 每章笔记见 [`notes/`](notes/)：`chNN-章节名.md`。

## 学习方式约定

- 先读官方文档对应章节（我已在每章笔记中给出链接）。
- 我在对话中讲解概念、梳理逻辑、补充示例；你随时提问。
- 建议在本地 MATLAB R2024b 中动手运行官方 `openExample` 示例，动手 > 阅读。

## 环境要求（动手实践时）

- MATLAB + Simulink（R2024b 或更新）
- Simulink Test（必装）
- 按章节需要：Stateflow、Simulink Coverage、Simulink Design Verifier、
  Requirements Toolbox、Embedded Coder、Simulink Real-Time、MATLAB Test 等。
  > 注意：本工作区当前没有 MATLAB 环境，实践步骤需在你的本机 MATLAB 中完成。
