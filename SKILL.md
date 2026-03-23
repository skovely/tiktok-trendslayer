---
name: tiktok-trend-slayer
description: TikTok 选品猎手 - 自动监控 TikTok Shop 商品榜与达人榜，利用 AI 挖掘高增长爆款，生成选品及达人撮合策略。当用户需要 TikTok 选品分析、爆款挖掘、达人匹配、趋势监控时使用此技能。需要配置 TIKTOK_SHOP_API_KEY 和 ECHOTIK_TOKEN 环境变量。
---

# TikTok 选品猎手

自动监控 TikTok Shop 商品榜与达人榜，挖掘高增长爆款，生成选品及达人撮合策略。

## 功能概述

1. **实时监控** - 调用 TikTok Shop Open API 和 EchoTik 接口获取商品/达人数据
2. **爆款识别** - 识别 GMV 增速前 5% 商品及 24h 销量翻倍的黑马 SKU
3. **AI 分析** - 分析爆款视频 Hook 和视频结构
4. **达人匹配** - 匹配高互动率中小达人（KOC）
5. **报告生成** - 输出 JSON/Markdown 格式的选品报告

## 环境要求

**必需凭证（使用前必须配置）：**
- `TIKTOK_SHOP_API_KEY` - TikTok Shop API 密钥（申请地址：https://partner.tiktokshop.com/）
- `ECHOTIK_TOKEN` - EchoTik API Token（申请地址：https://www.echotik.com/）

**系统依赖：**
- `curl` - HTTP 请求工具
- `jq` - JSON 处理工具

## 使用方法

### 配置凭证

```bash
# 设置环境变量
export TIKTOK_SHOP_API_KEY="your_app_key"
export ECHOTIK_TOKEN="your_token"
```

### 执行选品分析

```bash
# 分析指定品类（beauty/3c/home）
./scripts/tiktok_slayer.sh --category beauty

# 分析所有重点品类
./scripts/tiktok_slayer.sh --all

# 查找黑马商品（24h 销量翻倍）
./scripts/tiktok_slayer.sh --black-horse

# 生成 Markdown 格式报告
./scripts/tiktok_slayer.sh --category beauty --format md
```

### 设置定时监控

```bash
# 添加到 crontab，每天 8:00 执行
0 8 * * * cd /path/to/tiktok-trend-slayer && ./scripts/tiktok_slayer.sh --all >> logs/cron.log 2>&1
```

## 输出格式

报告包含以下字段：
- `product_name` - 商品名称
- `product_image` - 商品主图 URL
- `current_sales` - 当前销量
- `gmv_growth` - GMV 增长率
- `estimated_profit` - 预估利润
- `recommended_creators` - 推荐达人列表
- `viral_keywords` - 爆火关键词
- `video_hooks` - 视频 Hook 分析


 ## 重点监控品类（TikTok Shop ID | EchoTik Code）
=======
## 重点监控品类（TikTok Shop ID | EchoTik Code）
>>>>>>> e25252af74c237b0bfb7738bb462bab9382a9b79
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

## 参考文档

- [API 文档](references/api_docs.md) - TikTok Shop API 和 EchoTik API 详细说明
- [输出示例](references/output_example.md) - 报告格式示例
