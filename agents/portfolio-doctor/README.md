# 持仓体检官 · Portfolio Doctor 🩺📊

> 把你的美股持仓丢进去，AI 给你做一次组合「体检」。
> 只挑毛病，不替你做决定 —— **帮你少亏钱，而不是帮你赚快钱。**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![Built with CREAO](https://img.shields.io/badge/Built%20with-CREAO-7c5cff.svg)](https://creao.ai)
[![Agent](https://img.shields.io/badge/Type-AI%20Agent-00b894.svg)](#)

本项目使用 **[CREAO](https://creao.ai)** 平台搭建，零后端代码——人设、规则、记忆全部由 CREAO 的 skill / memory 配置提供。是「美股老司机」系列的第二个 Agent，专攻**组合层面的风险**。

---

## ✨ 它解决什么问题

散户最大的坑不是选错票，而是**仓位结构烂**：
- 3 只票全是 AI 算力，相关性 0.9，自以为分散了；
- 单股 30%，一只票绑架整个账户；
- 全是高 Beta，大盘一回调直接腰斩。

「持仓体检官」就是来挑这些毛病的。

---

## 🩺 五项体检

| 体检项 | 看什么 |
|--------|--------|
| **集中度** | 单股 >20%、单板块 >40% 预警；是否押注单一主线 |
| **相关性（伪分散）** | 表面多只票，实则高相关同涨同跌（如 NVDA/AMD/SMCI） |
| **回撤敞口** | 用加权 Beta 估算「大盘跌 20% 时组合大概亏多少」 |
| **再平衡建议** | 该减谁、补什么类型（不给具体买点） |
| **健康分** | 0-10 综合打分，一眼看组合稳不稳 |

---

## 📥 输入字段

| 字段 | 类型 | 必填 | 说明 |
|------|------|------|------|
| `holdings` | textarea | ✅ | 每行一只，带占比或市值，如 `NVDA 30%; AMD 15%; 现金 20%` |
| `risk_profile` | select | ❌ | 保守 / 稳健 / 进取 |
| `capital` | string | ❌ | 总资金，用于把回撤敞口折算成金额 |

---

## 📤 输出格式（固定五段式）
```
① 一句话体检结论（组合最大的问题是什么）
② 关键发现（集中度/相关性/回撤敞口，带数据）
③ 风险提示（最危险的敞口）
④ 行动建议（该减谁、补什么、单股上限、再平衡方向）
⑤ 一句吐槽
```

---

## 🚀 快速开始
1. 打开 [CREAO](https://creao.ai)
2. 导入 [`agent/config.yaml`](./agent/config.yaml) 与 [`agent/skill.md`](./agent/skill.md)
3. 填入持仓即可体检

或直接把 `agent/skill.md` 当 system prompt 投喂给任意 LLM。

---

## 🚫 红线（硬约束）
- 不推荐具体买入价、不保证收益
- 不鼓励重仓、杠杆、All in
- **不替你做买卖决定**，只给框架和风险
- 不传播未验证小道消息

## ⚠️ 免责声明
仅供学习研究，**不构成任何投资建议**。DYOR。

## 📄 License
[MIT](./LICENSE)
