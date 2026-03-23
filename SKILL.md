---
name: tiktok-trend-slayer
description: TikTok 选品猎手 - 自动监控 TikTok Shop 商品榜与达人榜，利用 AI 挖掘高增长爆款，生成选品及达人撮合策略。当用户需要 TikTok 选品分析、爆款挖掘、达人匹配、趋势监控时使用此技能。
---

# TikTok 选品猎手

自动监控 TikTok Shop 商品榜与达人榜，挖掘高增长爆款，生成选品及达人撮合策略。

**适用场景**：
- TikTok Shop 卖家选品决策
- 跨境电商从业者监控竞品动态
- 达人营销寻找高转化商品
- 供应链选品调研

---

## ✨ 核心功能

| 功能 | 说明 |
|------|------|
| 📊 **实时监控** | 每天 8:00 自动调用 TikTok API + EchoTik 获取商品/达人数据 |
| 🔥 **爆款识别** | 筛选 GMV 增速前 5% 商品 + 24h 销量翻倍的黑马 SKU |
| 🤖 **AI 分析** | 分析爆款视频 Hook（3秒反转、Before/After、数字冲击） |
| 👥 **达人匹配** | 自动匹配互动率 > 5% 的中小达人（10K-100K 粉丝） |
| 📝 **报告输出** | JSON / Markdown 双格式，包含商品图、销量、利润、关键词、推荐达人 |

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

## 重点监控品类（TikTok Shop ID | EchoTik Code）
- 美妆护肤	10001	beauty
- 3C数码	10002	3c
- 家居生活	10003	home
- 服装配饰	10004	fashion
- 食品饮料	10005	food
- 运动户外	10006	sports
- 母婴用品	10007	baby
- 宠物用品 10008 pet 

## 达人匹配标准

- 粉丝量：1K-100K（中小达人/KOC）
- 互动率：> 5%
- 品类垂直度：与商品品类匹配

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

- **版本**: 0.1.4
- **作者**: anandaely
- **更新日期**: 2026-03-23
- **依赖**: curl, jq, TIKTOK_SHOP_API_KEY, ECHOTIK_TOKEN

---

## 🏷️ 标签

`tiktok` `选品` `电商` `达人营销` `数据分析` `TikTok Shop` `跨境电商` `爆款挖掘`

---

*安装方式：把 .skill 文件放入 ~/.openclaw/skills/ 目录，或使用 `npx clawhub@latest install tiktok-trend-slayer`*


## 参考文档

- [API 文档](references/api_docs.md) - TikTok Shop API 和 EchoTik API 详细说明
- [输出示例](references/output_example.md) - 报告格式示例
