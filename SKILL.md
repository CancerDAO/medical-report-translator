---
name: cancerdao-medical-report-translator
description: "当患者上传病理报告、基因检测报告、影像报告并请求翻译时使用。不是逐字解释，而是回答'这句话什么意思？严重吗？下一步怎么办？'输出结构化翻译（一句话总结+逐项解释+严重程度评估+下一步建议）。触发词：病理报告、基因检测、影像报告、看不懂、什么意思、Ki-67、分化、侵犯、突变、报告翻译。"
license: MIT
metadata:
  author: CancerDAO
  version: "2.0.0"
  tags: medical-translation pathology genomics oncology
---

# CancerDAO Medical Report Translator

把病理报告、基因检测报告、影像报告翻译成患者能看懂的大白话。

## When to use

- 发送病理/基因/影像报告请求翻译
- 问"看不懂"、"什么意思"、"帮我看看"
- 提到专业术语：Ki-67、分化、侵犯、突变

## Outputs — 结构化翻译

1. **一句话总结** — 第一时间知道是好消息还是坏消息
2. **逐项解释** — 原始术语 → 通俗解释 + 临床意义
3. **严重程度评估** — 低/中/高（不使用分期术语）
4. **下一步建议** — 和医生讨论什么
5. **安全免责声明**

## 报告类型

### 病理报告

| 术语 | 通俗化 |
|---|---|
| 低/中/高分化 | 恶性程度高/中/低 |
| 脉管侵犯阳性 | 有向血管/淋巴管扩散的迹象 |
| 神经侵犯阳性 | 肿瘤已侵入神经 |
| 切缘阴性 | 手术切除干净 |
| Ki-67 >30% | 生长速度较快 |

### 基因检测报告

| 突变 | 功能解释 |
|---|---|
| EGFR 19del/L858R | 经典靶向突变，一线可用奥希替尼 |
| ALK融合 | "钻石突变"，靶向药效果显著 |
| KRAS G12C | 曾不可成药，现有多款新药 |
| TP53突变 | 肿瘤抑制基因失活，预后相对差 |
| MSI-H/dMMR | 可能从PD-1抑制剂获益 |
| TMB | 突变负荷，越高免疫效果可能越好 |
| PD-L1 TPS >50% | 免疫治疗敏感度高，单药可能有效 |

### 影像报告

| 术语 | 通俗解释 |
|---|---|
| 多发结节 | 可能有转移，需全身检查 |
| 纵隔淋巴结肿大 | 分期上升，需进一步评估 |
| 胸腔积液 | 需穿刺确认性质 |
| 肝/骨/脑转移 | 晚期，治疗目标转为延长生存 |

## Safety Guidelines

1. 不替代医生 — 仅供理解参考
2. 不给具体用药建议
3. 每份翻译结尾建议"和医生讨论具体治疗方案"
4. 用鼓励、希望的语气，避免夸大严重程度
5. 不主动给出具体分期

## References

- `references/pathology-terms.md` — 肿瘤分级、侵犯、淋巴结
- `references/gene-terms.md` — EGFR/ALK/KRAS/TP53/MET 等
- `references/imaging-terms.md` — CT/MRI 术语、RECIST
- `references/ki67-interpretation.md` — Ki-67 cutoffs
- `references/biomarker-interpretation.md` — TMB、PD-L1、MSI

## File map

```
cancerdao-medical-report-translator/
├── SKILL.md
├── README.md
├── evals/
│   ├── evals.json
│   └── files/
└── references/
    ├── pathology-terms.md
    ├── gene-terms.md
    ├── imaging-terms.md
    ├── ki67-interpretation.md
    └── biomarker-interpretation.md
```
