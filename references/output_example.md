# TikTok 选品猎手 - 输出示例

## JSON 报告格式

```json
{
  "report_meta": {
    "generated_at": "2026-03-21T08:00:00Z",
    "category": "beauty",
    "source": ["tiktok_shop", "echotik"],
    "version": "1.0.0"
  },
  "top_products": [
    {
      "rank": 1,
      "product_id": "P123456789",
      "name": "Vitamin C Brightening Serum",
      "product_image": "https://example.com/images/serum.jpg",
      "current_sales": 25800,
      "sales_24h": 3200,
      "sales_7d": 18500,
      "gmv_growth": "+67%",
      "estimated_profit": "$4,200",
      "price": 24.99,
      "rating": 4.6,
      "review_count": 3200,
      "viral_keywords": ["vitamin_c", "brightening", "skincare", "glow_up", "affordable"],
      "recommended_creators": [
        {
          "id": "C789012",
          "name": "SkincareWithSarah",
          "followers": 28000,
          "engagement_rate": 0.082,
          "avg_views": 8500,
          "category": "beauty",
          "match_score": 0.92
        },
        {
          "id": "C789013",
          "name": "GlowGetter_Lisa",
          "followers": 45000,
          "engagement_rate": 0.068,
          "avg_views": 12000,
          "category": "beauty",
          "match_score": 0.88
        }
      ],
      "video_hooks": {
        "primary": "3秒反转",
        "secondary": "Before/After",
        "structure": "Problem -> Solution -> Social Proof -> CTA",
        "examples": [
          "你以为这只是普通精华？看看我7天的变化！",
          "暗沉肌逆袭！这个维C精华让我白了2个度",
          "皮肤科都在推的平价精华，效果不输大牌"
        ]
      },
      "competitive_analysis": {
        "market_saturation": "medium",
        "price_positioning": "mid_range",
        "differentiation": "high_concentration_vitamin_c"
      }
    },
    {
      "rank": 2,
      "product_id": "P123456790",
      "name": "Wireless LED Makeup Mirror",
      "product_image": "https://example.com/images/mirror.jpg",
      "current_sales": 19200,
      "sales_24h": 2100,
      "sales_7d": 12800,
      "gmv_growth": "+45%",
      "estimated_profit": "$3,800",
      "price": 39.99,
      "rating": 4.4,
      "review_count": 2100,
      "viral_keywords": ["led_mirror", "makeup_essential", "travel_friendly", "dimmable"],
      "recommended_creators": [
        {
          "id": "C789014",
          "name": "MakeupByMia",
          "followers": 35000,
          "engagement_rate": 0.071,
          "avg_views": 9800,
          "category": "beauty",
          "match_score": 0.90
        }
      ],
      "video_hooks": {
        "primary": "数字冲击",
        "secondary": "场景代入",
        "structure": "Hook -> Feature Demo -> Use Case -> Price Reveal",
        "examples": [
          "3个功能让我放弃了我500块的化妆镜！",
          "出差必带！这个镜子让我在哪都能化出完美妆容",
          "终于找到不晃眼的LED镜了，化妆细节看得清清楚楚"
        ]
      }
    }
  ],
  "black_horse_products": [
    {
      "product_id": "P999888777",
      "name": "Silicone Face Cleansing Brush",
      "sales_24h": 850,
      "sales_7d_avg": 120,
      "growth_multiplier": 7.08,
      "reason": "24h销量是7日均值的7倍，疑似爆款启动",
      "alert_level": "high"
    }
  ],
  "insights": {
    "trending_category": "beauty",
    "avg_growth_rate": "+56%",
    "top_performing_hook": "3秒反转",
    "recommended_action": "重点关注维C精华品类，建议与互动率>7%的KOC合作",
    "market_trends": [
      "成分党崛起，维C、烟酰胺等有效成分产品增长迅速",
      "便携美妆工具需求上升，LED镜、迷你刷具销量增长",
      "价格敏感度提高，50美元以下产品转化率更高"
    ]
  }
}
```

---

## Markdown 报告格式

```markdown
# TikTok 选品猎手报告

**生成时间**: 2026-03-21 08:00:00  
**监控品类**: 美妆护肤  
**数据来源**: TikTok Shop, EchoTik

---

## 🏆 爆款商品 TOP 5

### #1 Vitamin C Brightening Serum

| 指标 | 数值 |
|------|------|
| 当前销量 | 25,800 |
| 24h销量 | 3,200 |
| GMV 增速 | **+67%** 🔥 |
| 预估利润 | $4,200 |
| 售价 | $24.99 |
| 评分 | ⭐ 4.6 (3,200评价) |

**爆火关键词**: #vitamin_c #brightening #skincare #glow_up #affordable

**推荐达人**:
1. **SkincareWithSarah** - 28K粉丝, 8.2%互动率, 匹配度 92%
2. **GlowGetter_Lisa** - 45K粉丝, 6.8%互动率, 匹配度 88%

**视频 Hook 策略**:
- 🎯 **3秒反转**: "你以为这只是普通精华？看看我7天的变化！"
- 📊 **Before/After**: "暗沉肌逆袭！这个维C精华让我白了2个度"
- 💡 **数字冲击**: "皮肤科都在推的平价精华，效果不输大牌"

---

### #2 Wireless LED Makeup Mirror

| 指标 | 数值 |
|------|------|
| 当前销量 | 19,200 |
| 24h销量 | 2,100 |
| GMV 增速 | **+45%** |
| 预估利润 | $3,800 |
| 售价 | $39.99 |
| 评分 | ⭐ 4.4 (2,100评价) |

**爆火关键词**: #led_mirror #makeup_essential #travel_friendly #dimmable

---

## 🐎 黑马商品预警

| 商品 | 24h销量 | 7日均值 | 增长倍数 | 预警级别 |
|------|---------|---------|----------|----------|
| Silicone Face Cleansing Brush | 850 | 120 | **7.08x** | 🔴 High |

> ⚠️ 该商品24h销量是7日均值的7倍，疑似爆款启动，建议立即跟进！

---

## 📊 品类洞察

- **平均增速**: +56%
- **最佳 Hook 类型**: 3秒反转
- **建议行动**: 重点关注维C精华品类，建议与互动率>7%的KOC合作

### 市场趋势

1. 🧪 **成分党崛起** - 维C、烟酰胺等有效成分产品增长迅速
2. ✈️ **便携美妆工具** - LED镜、迷你刷具销量增长
3. 💰 **价格敏感度提高** - 50美元以下产品转化率更高

---

## 🎯 达人匹配策略

### 优先合作特征

- ✅ 粉丝量: 10K-100K (KOC)
- ✅ 互动率: > 5%
- ✅ 品类垂直度: 与商品强相关
- ✅ 近期视频平均播放量: > 5K

### 避坑指南

- ❌ 避免粉丝量>500K的头部达人（性价比低）
- ❌ 互动率<3%的账号（可能是僵尸粉）
- ❌ 近期有负面舆情或争议内容的达人

---

*报告由 TikTok Trend Slayer 自动生成*
```

---

## 字段说明

| 字段名 | 类型 | 说明 |
|--------|------|------|
| product_id | string | 商品唯一标识 |
| name | string | 商品名称 |
| current_sales | int | 当前总销量 |
| sales_24h | int | 近24小时销量 |
| sales_7d | int | 近7天销量 |
| gmv_growth | string | GMV增长率 |
| estimated_profit | string | 预估利润 |
| viral_keywords | array | 爆火关键词标签 |
| recommended_creators | array | 推荐达人列表 |
| video_hooks | object | 视频Hook分析 |
| match_score | float | 达人与商品匹配度 (0-1) |
| alert_level | string | 黑马预警级别 (low/medium/high) |
