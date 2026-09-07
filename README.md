# WhaleQuant A 股全自动量化实盘独立 Web 门户 (Quantitative Trading Web Portal)

> **定位**: 类似于 [`projects/interview_prep/domain_knowledge`](../interview_prep/domain_knowledge)，为 A 股自动化量化实盘打造的**纯静态、零依赖、现代化独立 Web 监控与投研门户**。
> **支持特性**: 100万稳健底仓 vs 10万激进复利双账户一键切换、15分钟微观 Level-2 OFI 订单流盯盘、2年全真回测收益图谱、Brinson/Barra 因子归因、深度时序注意力与选股池动态管理。

---

## 🗺️ 门户目录结构

```
projects/quant_dashboard/
├── index.html                               # 🌟 全局独立静态单页门户 (直接用浏览器打开即可)
├── README.md                                # 📖 本说明文档
├── assets/                                  # 📊 高分辨率量化图表与可视化资产
│   ├── high_alpha_100k_backtest.png        # 10万激进策略 2年全真回测图 (+93.92%, 盈亏比 2.96:1)
│   ├── performance_attribution.png         # Brinson 行业归因与 Barra 风格因子损益分解
│   ├── deep_factor_attention.png           # PyTorch 深度时序多头自注意力权重图
│   └── stress_test_radar.png               # 极端情景压力测试与黑天鹅雷达图
└── data/                                    # 💾 结构化量化数据归档 (JSON)
    ├── intraday_snapshots.json             # 15分钟微观盘口与订单流快照
    ├── portfolio_state.json                # 100万稳健账户实时状态
    ├── portfolio_100k_state.json           # 10万激进账户实时状态
    ├── high_alpha_100k_report.json         # 10万激进策略全量回测指标
    └── universe_status.json                # 选股池动态生命周期 (准入/晋升/淘汰)
```

---

## 🚀 浏览与访问方式

### 1. 本地免服务器直接秒开 (Zero-Config Direct Viewing)
由于本门户所有样式 (TailwindCSS CDN)、图表库 (Chart.js)、字体图标 (FontAwesome) 以及核心初始数据均采用**自包含静态封装**，您可以直接在 macOS 终端中运行：
```bash
open projects/quant_dashboard/index.html
```
或者直接在 Finder 中双击 `index.html`，即可在任何浏览器中打开完整的动态仪表盘！

### 2. 本地实时守护服务 (带 15 分钟实时自动更新与后端控制)
如果您在本地后台启动了 Python 监控守护进程：
```bash
PYTHONPATH=projects/whale-quant/paper_trading projects/whale-quant/.venv/bin/python projects/whale-quant/paper_trading/web_dashboard.py 8088
```
可在浏览器中访问：**[http://localhost:8088](http://localhost:8088)**，支持网页端直接点击“⚡ 立即触发 15m 巡检”并与本地交易引擎联动。

---

## 🌐 线上独立 Public 仓库与 GitHub Pages 部署状态

本项目已作为独立 Public 仓库正式上线 GitHub，并启用原生 GitHub Pages：

- 📦 **GitHub 独立开源仓库**: [https://github.com/lizhong3232/quant-dashboard](https://github.com/lizhong3232/quant-dashboard)
- 🚀 **GitHub Pages 全球访问门户**: [https://lizhong3232.github.io/quant-dashboard/](https://lizhong3232.github.io/quant-dashboard/)
- 🔄 **自动同步脚本**: 本地运行 `./sync_to_github.sh` 即可在 2 秒内将最新的实盘对账快照与图表推送到 GitHub Pages。

