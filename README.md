# 口算冲刺

一个纯前端的口算练习页，打开就能用。零依赖、无构建、不上传任何数据。

在线：<https://feng-zimo.github.io/kousuan/>

## 功能

- **三档难度**
  - 一二年级：20 以内加减（含进位、退位）
  - 三四年级：100 以内加减 + 表内乘除
  - 五六年级：两步混合（带括号）、两位数乘一位数、一位小数加减
- **题量** 10 / 20 / 50
- **两种模式**：练习（答错给看正确答案）、限时（每题 12 秒）
- 即时判分、连对计数、进度条、计时
- 结算卡：得分、用时、平均每题、最长连对、错题回顾（你的答案 → 正确答案）
- `localStorage` 记本机最好成绩，按「难度 + 题量 + 模式」分别存
- 键盘直接敲数字，<kbd>Enter</kbd> 提交并下一题，<kbd>Esc</kbd> 提前结束；手机也能用

## 出题约束

- 减法结果不为负、除法一定整除、小数结果保留一位
- 每档题目去重，50 题不会反复撞同一道
- 混合运算用括号明确优先级，不靠「先乘后加」的默契

## 技术

单个 `index.html`，CSS / JS 全内联，无框架、无 CDN、无外部字体。
题目只在本机生成，答案只在本机比对——没有后端，也没有网络请求（除了打开页面本身）。

本地跑：

```bash
python3 -m http.server 8000
# 打开 http://localhost:8000/
```

直接双击 `index.html` 也能用（没有 ES Modules，`file://` 下正常）。

## 构建与部署

用 [github-skills](https://github.com/Cool-zimo/github-skills-lab) 一条龙推上来：

```bash
github new repo kousuan
github sync . -m "feat: 口算练习 page"
github verify .
```

## 许可

MIT
