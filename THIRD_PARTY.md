# THIRD-PARTY NOTICES

本仓库的方案建立在下述**公开开源项目**之上。所有上游组件的著作权归其原作者，本仓库仅以与其许可兼容的方式使用，并按许可要求在此署名。

---

## 1. Tufa Labs — Duck harness

- **用途**：Agent harness 基础架构（交互循环、动作空间、游戏封装）
- **来源**：Kaggle Notebook `jeroencottaar/tufa-labs-duck-harness-june-30-milestone-winner`
- **作者**：Harold Bessis, Jeroen Cottaar, Isaiah Pressman, Andries Smit, Michal Tesnar, Stefano Viel
- **许可**：Apache License 2.0
- **说明**：ARC Prize 2025 June-30 Milestone 获奖方案

## 2. Daniel Franzen — "Milestone-2" harness 补丁

- **用途**：Duck harness 的改进补丁；本仓库两份提交的基座
- **来源**：Kaggle Notebook `dfranzen/…`（M2 系列）及 `dfranzen/intel-qwen3.8-flash-next-w4a16-autoround` 模型
- **作者**：Daniel Franzen
- **许可**：Apache License 2.0
- **说明**：本仓库 `arc3-form-d1-t55.ipynb` 为其 harness 的衍生版本，改动见 README §3.1

## 3. shiiin9 — D' 槽位优先级调度（仅作对照，未采用）

- **用途**：**对照实验**对象。我们的实测与公开对照均显示其为负收益，最终提交未使用
- **来源**：Kaggle Notebook `shiiin9/…`（D' 系列）
- **作者**：shiiin9（大阪公立大学团队）
- **许可**：Apache License 2.0
- **说明**：README §3.3 引用了其公开的对照数据（lalalia 33.94 → 加 D' 23.57）

## 4. Vickyfym — lalalia 强记忆基座

- **用途**：`arc3-slm-plus-v2.ipynb` 的基座（关卡记忆：30 动作 + 900 字符推理 + 最近 3 关全文）
- **来源**：Kaggle Notebook `vickyfym/arc-agi-3-lalalia-final`（V1）
- **作者**：Vickyfym
- **许可**：Apache License 2.0
- **说明**：我们曾以其 V1 版本作逐字节对照实验（md5 一致），并在其基座上叠加 `form_priority` 补丁与超时修复

## 5. 模型权重

- **`dfranzen/intel-qwen3.8-flash-next-w4a16-autoround`**
  - 基座模型：Qwen3.8-Flash-Next（阿里巴巴通义千问团队），按其原始许可使用
  - 量化/打包：Daniel Franzen（Apache-2.0）
- 本仓库**不分发任何模型权重**，仅在复现步骤中引用 Kaggle 上的公开模型数据集。

## 6. 竞赛数据

- ARC-AGI-3 竞赛数据（`arc_agi_3_wheels`、`environment_files`）由 ARC Prize Foundation 通过 Kaggle 提供。
- 本仓库**不包含**任何竞赛数据或其派生数据集；notebook 中的 `/kaggle/input/competitions/...` 为运行时挂载路径。

---

## 我们的改动范围

相对上述上游，本仓库的全部改动为：

| 文件 | 相对上游的改动 |
|---|---|
| `notebooks/arc3-form-d1-t55.ipynb` | 2 行：`SERVER_STARTUP_TIMEOUT` 720→3300；`ARC3_HTTP_RETRY_INITIAL_SECONDS` 900→3600 |
| `notebooks/arc3-slm-plus-v2.ipynb` | 上游 `arc3-slm-plus` v2 原样，未改动 |

**除此之外未修改任何算法逻辑。** 我们的工作主要在于分析、对照实验与提交策略（见 README §3）。

---

如有署名遗漏或署名方式不当，请通过 GitHub Issue 指出，我们会立即更正。
