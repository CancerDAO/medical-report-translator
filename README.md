# CancerDAO Medical Report Translator

医学报告人话翻译 skill。把病理/基因/影像报告翻译成患者能看懂的大白话。

## Install

```bash
npx skills add CancerDAO/medical-report-translator
```

## When to use

- 拿到病理报告看不懂
- 基因检测报告不知道怎么解读
- CT/MRI 报告写了什么

## Key features

- 结构化翻译（一句话总结 + 逐项解释 + 严重程度 + 下一步）
- 术语 → 大白话映射（Ki-67、分化、脉管侵犯、EGFR突变等）
- 不判断分期，只描述严重程度
- 每份翻译附医生讨论建议

## Examples

输入：`低分化腺癌，侵及浆膜层，淋巴结转移4/12，脉管侵犯阳性`

输出：
- 一句话总结：分期偏晚、恶性程度较高，需要积极治疗
- 逐项解释每个术语
- 严重程度：高
- 下一步建议和医生讨论

MIT — CancerDAO
