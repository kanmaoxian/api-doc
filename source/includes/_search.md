# 搜索

## 热搜

```ruby

content = RestClient.get '/v1/search_histories/popular'， {category: 'today'}
```

```json

{
  "data": [
    "鬼吹灯"
  ],
  "meta": {
    "code": 10000,
    "message": "Success"
  }
}
```

查看热搜关键字

### 接口

GET /v1/search_histories/popular

### 参数

名称 | 必须| 默认 | 描述
--------- | -------| ------- | -----------
category |  false| week | 搜索时间区间，支持 today, week, month, year


### 返回

名称 | 描述
--------- | -------
data|数据信息
meta|元数据信息