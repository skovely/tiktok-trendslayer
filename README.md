## 🎯 技能介绍

**TikTok Trend Slayer** **TK 选品猎手**是一款面向 TikTok 电商卖家的智能选品工具。通过自动监控 TikTok Shop 商品榜、EchoTik 数据接口，实时识别高增长爆款商品，并利用 AI 分析爆款视频的钩子（Hook）与结构，自动匹配合适的中腰部达人（KOC），帮助卖家快速发现蓝海品类与合作机会。

**【为什么选择 TikTok Trend Slayer？】**

在 TikTok 电商领域，领先 48 小时发现爆款意味着 10 倍的利润空间。传统的选品工具只告诉你“什么火了”，而 ***TikTok Trend Slayer*** 告诉你“什么即将火”以及“为什么火”。将原本需要 3 小时的手动刷榜和分析，缩短为 1 分钟的“选品简报”。

**👥【适用人群及场景】**
* **跨境卖家***：寻找高毛利、低竞争的 3C、美妆、家居黑马产品。
* **MCN 机构***：快速为旗下达人匹配高转化 SKU，缩短测品周期。
* **独立站玩家***：捕捉社媒流行趋势，实现流量套利。
* **供应链***：挖掘蓝海品类和调研。


**🎯【核心功能特性】**
* **🚀 黑马发现算法***：实时监测 GMV 增长斜率。当某个商品在 24 小时内销量增速翻倍，且挂车达人数仍处于低位时，系统将自动触发“蓝海预警”。
* **🎭 视频病毒基因拆解***：AI 自动解析高转化视频的“黄金 3 秒”Hook、脚本结构与 BGM 情绪，为您提供 1:1 可复刻的爆款脚本公式。
* **👥 达人撮合雷达***：基于商品画像自动筛选最具带货潜力的 KOC，拒绝只看粉丝数，只看实战转化率。
* **📊 自动选品报告***：支持导出包含商品图、当前销量、预估利润、竞争程度及推荐话术的完整报告。

---

## 📦 包含内容

```
tiktok-trend-slayer/
├── SKILL.md                    # 技能主文档
├── scripts/
│   └── tiktok_slayer.sh       # 选品分析脚本（自动生成报告）
└── references/
    ├── api_docs.md            # TikTok Shop API + EchoTik API 接口文档
    └── output_example.md      # JSON / Markdown 输出格式示例
```

---

## 🚀 快速开始

### 1. 环境准备

```bash
# 安装依赖
brew install curl jq

# 设置 API 密钥
export TIKTOK_SHOP_API_KEY="your_tiktok_shop_app_key"
export ECHOTIK_TOKEN="your_echotik_token"
```

### 2. 运行选品分析

```bash
# 分析指定品类
~/.qclaw/workspace/skills/tiktok-trend-slayer/scripts/tiktok_slayer.sh --category beauty

# 分析所有重点品类（3C、美妆、家居）
~/.qclaw/workspace/skills/tiktok-trend-slayer/scripts/tiktok_slayer.sh --all

# 生成 Markdown 报告
~/.qclaw/workspace/skills/tiktok-trend-slayer/scripts/tiktok_slayer.sh --category beauty --format md
```

### 3. 设置定时任务

```bash
# 每天 8:00 自动执行
crontab -e
0 8 * * * ~/.qclaw/workspace/skills/tiktok-trend-slayer/scripts/tiktok_slayer.sh --all >> ~/.qclaw/workspace/skills/tiktok-trend-slayer/logs/cron.log 2>&1
```

---

## 📋 输出示例

### JSON 报告

```json
{
  "report_meta": {
    "category": "beauty",
    "generated_at": "2026-03-23T08:00:00Z"
  },
  "top_products": [
    {
      "rank": 1,
      "name": "Vitamin C Brightening Serum",
      "current_sales": 25800,
      "gmv_growth": "+67%",
      "estimated_profit": "$4,200",
      "viral_keywords": ["vitamin_c", "brightening", "glow_up"],
      "video_hooks": {
        "primary": "3秒反转",
        "structure": "Problem -> Solution -> Social Proof"
      }
    }
  ]
}
```

### Markdown 报告

```markdown
# TikTok 选品猎手报告

## 🏆 爆款商品 TOP 5

| 排名 | 商品名称 | 当前销量 | GMV 增速 | 预估利润 |
|------|----------|----------|----------|----------|
| 1 | Vitamin C Serum | 25,800 | +67% | $4,200 |
| 2 | LED Makeup Mirror | 19,200 | +45% | $3,800 |

## 🎯 推荐达人

- **SkincareWithSarah** - 28K 粉丝, 8.2% 互动率
- **GlowGetter_Lisa** - 45K 粉丝, 6.8% 互动率
```

---

## 🔑 API 申请

| API | 申请地址 | 获取密钥 |
|-----|----------|----------|
| TikTok Shop Partner | https://seller.tiktokglobalshop.com/ | App Key + App Secret |
| EchoTik | https://www.echotik.com/ | API Token |

---

## 📌 版本信息

- **版本**: 0.1.7
- **作者**: anandaely
- **更新日期**: 2026-03-23
- **依赖**: curl, jq, TIKTOK_SHOP_API_KEY, ECHOTIK_TOKEN

---

## 🏷️ 标签

`tiktok` `选品` `电商` `达人营销` `数据分析` `TikTok Shop` `跨境电商` `爆款挖掘`

---

*安装方式：把 .skill 文件放入 ~/.openclaw/skills/ 目录，或使用 `npx clawhub@latest install tiktok-trend-slayer`*
