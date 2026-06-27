# Activity-Based Time Study Calculator — Warehouse Picking

### A single-file, browser-based tool for conducting activity-based time studies on warehouse picking operations. No installation, no build step — just open `index.html` in any browser.
---

<img width="700" height="400" alt="Image" src="https://github.com/user-attachments/assets/8d287e92-3c10-4061-8d6f-dad14424b28b" />

## Features

### Setup Tab
- Study metadata: name, analyst, picker, shift, date
- Picking method: RF Scanner, Voice Directed, Pick-to-Light, Paper, RFID
- Pick type: Single Order, Batch/Multi-Order, Zone, Cluster
- Equipment/MHE selection
- Configurable PF&D allowance %
- Add/remove custom activity codes with VA/NVA classification

### Record Tab
- Live stopwatch timer with **snapback** (measures each element) or **continuous** timing mode
- One-click activity buttons colour-coded by category
- Per-observation performance rating factor and notes
- Multi-round support — add rounds to separate study cycles
- Undo last observation

### Results Tab
- Per-activity statistics: count, average, std deviation, normal time, standard time
- Estimated picks per hour based on standard time + allowance
- Value-Added vs NVA-Necessary vs Non-Value-Added time breakdown
- Horizontal bar chart by activity
- Round comparison table (when multiple rounds recorded)
- **CSV export** with all observations and study metadata

---

## Default Activity Codes

| Code | Activity | Category |
|------|----------|----------|
| TT | Travel (Empty) | NVA-Necessary |
| TL | Travel (Loaded) | NVA-Necessary |
| LC | Locate / Search | Non-Value-Added |
| PK | Pick Item | Value-Added |
| SC | Scan / Verify | Value-Added |
| HA | Handle / Stage | Value-Added |
| WT | Wait / Idle | Non-Value-Added |
| AD | Admin / Label | NVA-Necessary |
| RE | Return to Start | NVA-Necessary |
| OT | Other | Non-Value-Added |

Custom codes can be added in the Setup tab.

---

## How to Use

1. Open `index.html` in a browser (or serve locally with `python3 -m http.server 8080`)
2. Fill in study details in the **Setup** tab
3. Go to the **Record** tab, press **Start**, then click activity buttons as the picker performs each task
4. View statistics and export results from the **Results** tab

### Timing Modes
- **Snapback** — each click records the elapsed time *since the last click*. Best for element-by-element studies.
- **Continuous** — each click records cumulative elapsed time. Duration is the time at the moment of click.

### Standard Time Calculation
```
Normal Time  = Observed Time × (Rating % / 100)
Standard Time = Normal Time × (1 + PF&D Allowance %)
```

---

## No Dependencies

The tool is self-contained vanilla HTML/CSS/JavaScript with no external libraries or CDN dependencies. It works offline and from a local file.

---

---

# 仓库拣货作业时间研究计算器（基于活动分析）

一款单文件浏览器工具，专为仓库拣货作业的活动时间研究设计。无需安装，无需构建，直接在任意浏览器中打开 `index.html` 即可使用。

---

## 功能特点

### 设置页（Setup）
- 研究基本信息：研究名称、分析员、拣货员、班次、日期
- 拣货方式：RF 扫描枪、语音引导、光导拣货、纸质单据、RFID
- 拣货类型：单订单、批量/多订单、分区拣货、集群拣货
- 设备/物料搬运设备选择
- 可配置 PF&D 宽放率（%）
- 自定义活动代码，支持增删及增值/非增值分类

### 记录页（Record）
- 实时秒表计时，支持**归零计时**（逐元素计时）和**累计计时**两种模式
- 一键记录活动，按类别颜色区分
- 每次观测可记录绩效评定系数及备注
- 支持多轮次——可新增轮次分隔不同研究周期
- 支持撤销上一条记录

### 结果页（Results）
- 各活动统计数据：观测次数、平均值、标准差、正常时间、标准时间
- 基于标准时间及宽放率估算每小时拣货量
- 增值时间 vs 必要非增值时间 vs 非增值时间占比分析
- 各活动水平条形图展示
- 多轮次对比表（记录多轮时显示）
- **CSV 导出**，包含所有观测数据及研究元信息

---

## 默认活动代码

| 代码 | 活动说明 | 类别 |
|------|----------|------|
| TT | 空载行走 | 必要非增值 |
| TL | 负载行走 | 必要非增值 |
| LC | 定位 / 寻找 | 非增值 |
| PK | 拣取货品 | 增值 |
| SC | 扫描 / 核验 | 增值 |
| HA | 搬运 / 暂存 | 增值 |
| WT | 等待 / 闲置 | 非增值 |
| AD | 行政 / 贴标 | 必要非增值 |
| RE | 返回起点 | 必要非增值 |
| OT | 其他 | 非增值 |

可在"设置页"中添加自定义活动代码。

---

## 使用方法

1. 在浏览器中打开 `index.html`（或通过 `python3 -m http.server 8080` 本地运行）
2. 在**设置页**填写研究基本信息
3. 进入**记录页**，按下**开始**，随拣货员操作点击对应活动按钮
4. 在**结果页**查看统计数据并导出结果

### 计时模式说明
- **归零计时** — 每次点击记录距上次点击的时间间隔，适合逐元素分析。
- **累计计时** — 每次点击记录当前累计时间，以点击时刻的时间为准。

### 标准时间计算公式
```
正常时间  = 观测时间 × （评定系数 / 100）
标准时间  = 正常时间 × （1 + PF&D 宽放率 %）
```

---

## 无外部依赖

本工具为纯 HTML/CSS/JavaScript 实现，无需任何外部库或 CDN，支持离线使用，可直接从本地文件运行。
