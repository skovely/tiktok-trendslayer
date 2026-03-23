# TikTok Shop API & EchoTik API 文档

## TikTok Shop Open API

### 基础信息

- **API 文档**: https://seller.tiktokglobalshop.com/university/zh-TW/article/TikTok-Shop-Open-API-Documentation
- **申请地址**: https://partner.tiktokshop.com/

### 认证方式

```bash
# 使用 App Key + App Secret 签名
app_key=your_app_key
timestamp=$(date +%s)
# 签名算法: MD5(app_key + timestamp + app_secret)
```

### 主要接口

#### 1. 获取商品列表

```http
GET /api/products/search
```

**参数**:
| 参数名 | 类型 | 必填 | 说明 |
|--------|------|------|------|
| app_key | string | 是 | 应用密钥 |
| timestamp | int | 是 | 时间戳 |
| sign | string | 是 | 签名 |
| category_id | string | 否 | 品类ID |
| page_size | int | 否 | 每页数量 |
| page_no | int | 否 | 页码 |

**响应示例**:
```json
{
  "code": 0,
  "message": "success",
  "data": {
    "products": [
      {
        "id": "123456789",
        "name": "Product Name",
        "category_id": "1234",
        "price": 19.99,
        "sales": 15000,
        "rating": 4.5
      }
    ],
    "total": 100
  }
}
```

#### 2. 获取商品详情

```http
GET /api/products/details
```

#### 3. 获取商品销量趋势

```http
GET /api/products/sales_trend
```

**参数**:
| 参数名 | 类型 | 必填 | 说明 |
|--------|------|------|------|
| product_id | string | 是 | 商品ID |
| start_date | string | 是 | 开始日期 (YYYY-MM-DD) |
| end_date | string | 是 | 结束日期 (YYYY-MM-DD) |

---

## EchoTik API

### 基础信息

- **官网**: https://echotik.com
- **API 文档**: https://echotik.com/api-docs
- **注册获取 Token**: https://echotik.com/register

### 认证方式

```bash
Authorization: Bearer your_echotik_token
```

### 主要接口

#### 1. 商品榜单

```http
GET /v1/products/ranking
```

**参数**:
| 参数名 | 类型 | 必填 | 说明 |
|--------|------|------|------|
| category | string | 否 | 品类 (beauty/3c/home/...) |
| period | string | 否 | 周期 (1d/7d/30d) |
| country | string | 否 | 国家代码 (US/UK/...) |
| page | int | 否 | 页码 |
| limit | int | 否 | 每页数量 |

**响应示例**:
```json
{
  "code": 200,
  "data": {
    "list": [
      {
        "product_id": "P123456",
        "name": "Product Name",
        "image": "https://...",
        "price": 29.99,
        "sales_7d": 25000,
        "sales_30d": 89000,
        "growth_rate": 0.58,
        "gmv_7d": 749750,
        "category": "Beauty"
      }
    ]
  }
}
```

#### 2. 达人搜索

```http
GET /v1/creators/search
```

**参数**:
| 参数名 | 类型 | 必填 | 说明 |
|--------|------|------|------|
| category | string | 否 | 主营品类 |
| min_followers | int | 否 | 最小粉丝数 |
| max_followers | int | 否 | 最大粉丝数 |
| min_engagement | float | 否 | 最小互动率 |
| country | string | 否 | 国家 |

**响应示例**:
```json
{
  "code": 200,
  "data": {
    "creators": [
      {
        "id": "C123456",
        "name": "Creator Name",
        "avatar": "https://...",
        "followers": 45000,
        "following": 500,
        "videos_count": 120,
        "engagement_rate": 0.075,
        "avg_views": 5000,
        "category": "Beauty",
        "country": "US"
      }
    ]
  }
}
```

#### 3. 视频分析

```http
GET /v1/videos/analyze
```

**参数**:
| 参数名 | 类型 | 必填 | 说明 |
|--------|------|------|------|
| video_id | string | 是 | 视频ID |
| include_transcript | bool | 否 | 是否包含字幕 |

**响应示例**:
```json
{
  "code": 200,
  "data": {
    "video_id": "V123456",
    "creator_id": "C123456",
    "views": 150000,
    "likes": 12000,
    "comments": 800,
    "shares": 450,
    "duration": 45,
    "hook_type": "3_second_twist",
    "structure": "problem_solution_proof",
    "viral_keywords": ["affordable", "must_have", "game_changer"],
    "transcript": "..."
  }
}
```

---

## 品类代码对照表

| 品类名称 | TikTok Shop ID | EchoTik Code |
|----------|----------------|--------------|
| 美妆护肤 | 10001 | beauty |
| 3C数码 | 10002 | 3c |
| 家居生活 | 10003 | home |
| 服装配饰 | 10004 | fashion |
| 食品饮料 | 10005 | food |
| 运动户外 | 10006 | sports |
| 母婴用品 | 10007 | baby |
| 宠物用品 | 10008 | pet |

---

## 错误码对照

| 错误码 | 说明 |
|--------|------|
| 0 | 成功 |
| 400 | 请求参数错误 |
| 401 | 认证失败 |
| 403 | 权限不足 |
| 429 | 请求频率超限 |
| 500 | 服务器错误 |

---

## 最佳实践

1. **缓存策略**: 商品数据建议缓存 1-4 小时，避免频繁调用 API
2. **错误处理**: 实现指数退避重试机制
3. **数据同步**: 使用 webhook 接收实时数据更新通知
4. **限流**: TikTok Shop API 默认 100 req/min，EchoTik 根据套餐不同
