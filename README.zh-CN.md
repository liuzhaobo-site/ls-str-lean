# LS 自校正调节论文的 Lean 形式化证明

对应 Zhaobo Liu 的论文 **LS-Based Self-Tuning Regulation with Unknown Input Gain for Arbitrary Bounded References**。

**[论文 PDF](paper/main.pdf)** · [LaTeX 源码](paper/main.tex) · [论文压缩包](paper/LS_STR_manuscript-2026-10-24.zip)

论文版本：**2026-10-24**。此版本晚于下方证明包中的论文快照；后续修订与 Lean 代码的对应关系尚未重新核对。

**[下载完整证明 ZIP](https://github.com/liuzhaobo-site/ls-str-lean/releases/download/proofs-2026-10-24/LS_STR_gram_covariance_v2-2026-10-24.zip)** · **[发布记录与校验文件](https://github.com/liuzhaobo-site/ls-str-lean/releases/tag/proofs-2026-10-24)** · [English](README.md)

ZIP 包含完整 Lean 源码、固定 LaTeX 原稿、原文与证明步骤映射、版本锁定、最终审计日志及复现工具。

## 结果范围

- 原整篇审计构建 **930 个模块**，检查 **3778 个声明**的完整类型、实际 theorem 身份和公理依赖；公理仅含标准三项。
- 原文 **31 项结果**中，**31 项全部 VERIFIED，公开类型均无 Guo/Tropp 外部前提**。
- 主定理包含 FIR/ARX 两个分支、有限初值和概率事件的拼接，得到残差能量 o(N)、回归能量 O(N)、输入输出平均能量有界及跟踪均方平均趋于噪声方差。
- 原 Lemma 5.2、真实事件构造中的 9/32 成功概率以及跟踪指标双向等价均已纳入。

本文需要的 Guo 最小二乘界和矩阵条件概率界已本地证明，并在主定理内部调用；不宣称重证完整文献的其他推广。旧接口的对数归一化和测度条件问题已修复，包内原始 LaTeX 未修改。

全部登记状态为 **3776 条 VERIFIED、2 条 PARTIAL/WEAKENED**。两条条件辅助引理是未使用的历史 Tropp 强版本，全部原稿结论均不依赖它们。历史总表仍保留严格 `success: false`、`whole_paper_verified: false`，实际内核和公理检查通过；31 项原稿结论及两个所需输入结果的验收通过。

## 查看和复现

解压后请阅读 `README.zh-CN.md`、`docs/RESULTS.md` 与 `docs/REPRODUCIBILITY.md`。环境固定为 Lean/Lake 4.24.0 和 Mathlib v4.24.0，所有传递依赖也固定提交。

ZIP 已通过原生解压、CRC、文件摘要、路径迁移和文件篡改拒绝测试。本次实际复查四个关键源码模块及 31 项原文结果的完整类型和公理，复用了固定工具链及编译导入；不是另一次全新机器安装或全量重编译。

原稿和证明源码保持原样。形式化与原文对应由 Codex 及协作代理完成；语义对应属于有记录的阅读审查，未宣称由机器自动证明或经独立人类审查。第三方署名和许可证保留在 ZIP 中，其余材料未擅自指定统一开源许可证。

ZIP 的 SHA-256 为：

```text
5bd973c28c7bf57170e36f5619b87300f51eeeb693fdcecbf6a1974e8551f04a
```
