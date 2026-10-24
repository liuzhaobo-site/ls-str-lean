# LS 自校正调节论文的 Lean 形式化证明

对应 Zhaobo Liu 的论文 **LS-Based Self-Tuning Regulation with Unknown Input Gain for Arbitrary Bounded References**。

**[论文 PDF](paper/main.pdf)** · [LaTeX 源码](paper/main.tex) · [论文压缩包](paper/LS_STR_manuscript-2026-10-24.zip)

论文版本：**2026-10-24**。此版本晚于下方证明包中的论文快照；后续修订与 Lean 代码的对应关系尚未重新核对。

**[下载完整证明 ZIP](https://github.com/liuzhaobo-site/ls-str-lean/releases/download/proofs-2026-10-24/LS_STR_gram_covariance_v2-2026-10-24.zip)** · **[发布记录与校验文件](https://github.com/liuzhaobo-site/ls-str-lean/releases/tag/proofs-2026-10-24)** · [English](README.md)

ZIP 包含完整 Lean 源码、固定 LaTeX 原稿、原文与证明步骤映射、版本锁定、最终审计日志及复现工具。

## 结果范围

- 原整篇审计构建 **913 个模块**，检查 **3696 个声明**的完整类型、实际 theorem 身份和公理依赖；公理仅含标准三项。
- 原文 **31 项结果**中，**20 项 VERIFIED，11 项保留作者接受的文献前提**。
- 主定理包含 FIR/ARX 两个分支、有限初值和概率事件的拼接，得到残差能量 o(N)、回归能量 O(N)、输入输出平均能量有界及跟踪均方平均趋于噪声方差。
- 原 Lemma 5.2、真实事件构造中的 9/32 成功概率以及跟踪指标双向等价均已纳入。

Guo（1995）原结论和 Tropp（2011）Lemma 2.1 按作者授权接受，作为 Lean 完整类型中的显式命题前提。本文的适用性推导与最终拼接已本地证明；本包没有重证这些文献结果，也没有新增自定义公理。

全部登记状态为 **3606 条 VERIFIED、90 条 PARTIAL/WEAKENED**。后者包含上述文献条件和历史窄范围辅助命题。因此，最终记录的内核与公理检查通过，但严格整篇 `success` 和 `whole_paper_verified` 仍为 `false`，不宣称无外部前提的整篇 VERIFIED。

## 查看和复现

解压后请阅读 `README.zh-CN.md`、`docs/RESULTS.md` 与 `docs/REPRODUCIBILITY.md`。环境固定为 Lean/Lake 4.24.0 和 Mathlib v4.24.0，所有传递依赖也固定提交。

ZIP 已通过原生解压、CRC、文件摘要、路径迁移和文件篡改拒绝测试。本次实际复查四个关键源码模块及 31 项原文结果的完整类型和公理，复用了固定工具链及编译导入；不是另一次全新机器安装或全量重编译。

原稿和证明源码保持原样。形式化与原文对应由 Codex 及协作代理完成；语义对应属于有记录的阅读审查，未宣称由机器自动证明或经独立人类审查。第三方署名和许可证保留在 ZIP 中，其余材料未擅自指定统一开源许可证。

ZIP 的 SHA-256 为：

```text
902700de0d98ffaf0ffa0705ef9642c5c9fbeb7d6452a7e8de348d1602bd840a
```
