# 榜单

## 列表

```ruby

content = RestClient.get 'https://example.com/v1/rankings'
```

```json

{
    "data": {
        "male": [
            {
                "id": 1,
                "name": "追书最热榜 Top100",
                "cover": "http://statics.zhuishushenqi.com/ranking-cover/142319144267827",
                "books_count": 197,
                "books": [
                    {
                        "id": "fpty7i85gxgg",
                        "name": "大主宰",
                        "author_name": "天蚕土豆",
                        "category_name": "玄幻",
                        "chapters_count": 0,
                        "cache_tags": "玄幻,热血,架空,异界大陆,巅峰,修炼,主宰",
                        "words": null,
                        "cover": "http://statics.zhuishushenqi.com/agent/http://image.cmfu.com/books/2750457/2750457.jpg",
                        "last_parsed_at": "2017-03-28T17:24:05.000+08:00",
                        "last_updated_at": "2017-03-28T17:24:05.000+08:00",
                        "description": "大千世界，位面交汇，万族林立，群雄荟萃，一位位来自下位面的天之至尊，在这无尽世界，演绎着令人向往的传奇，追求着那主宰之路。 无尽火域，炎帝执掌，万火焚苍穹。 武...",
                        "last_chapter": {
                            "updated_at": null,
                            "title": "第1496章 莫名来者"
                        }
                    },
                    ...
                ]
            },
            ...
        ],
        "female": [
            {
                "id": 15,
                "name": "追书最热榜 Top100",
                "cover": "http://statics.zhuishushenqi.com/ranking-cover/142319144267827/ranking-cover/142319314350435",
                "books_count": 177,
                "books": [
                    {
                        "id": "fpty7i85gxgg",
                        "name": "大主宰",
                        "author_name": "天蚕土豆",
                        "category_name": "玄幻",
                        "chapters_count": 0,
                        "cache_tags": "玄幻,热血,架空,异界大陆,巅峰,修炼,主宰",
                        "words": null,
                        "cover": "http://statics.zhuishushenqi.com/agent/http://image.cmfu.com/books/2750457/2750457.jpg",
                        "last_parsed_at": "2017-03-28T17:24:05.000+08:00",
                        "last_updated_at": "2017-03-28T17:24:05.000+08:00",
                        "description": "大千世界，位面交汇，万族林立，群雄荟萃，一位位来自下位面的天之至尊，在这无尽世界，演绎着令人向往的传奇，追求着那主宰之路。 无尽火域，炎帝执掌，万火焚苍穹。 武...",
                        "last_chapter": {
                            "updated_at": null,
                            "title": "第1496章 莫名来者"
                        }
                    },
                    ...
                ]
            },
            ...
        ]
    },
    "meta": {
        "code": 10000,
        "message": "Success"
    }
}
```

返回所有的榜单，按男女分组

### 接口

/v1/rankings

### 参数

名称 | 是否必须| 默认 | 描述
--------- | -------| ------- | -----------
children | false| | 是否包含书明细

### 返回

名称 | 描述
--------- | -------
data|数据信息
meta|元数据信息
male|男生榜单
female|女生榜单
id|榜单 ID
name|榜单名称
cover|榜单封面
books_count|榜单书量
books|书明细，注意，如果children不传，则无此 tag
code|执行状态码，10000 为成功执行
message|执行状态说明


## 明细

```ruby

content = RestClient.get 'https://example.com/v1/rankings/1'
```

```json

{
    "data": [
        {
            "id": "fpty7i85gxgg",
            "name": "大主宰",
            "author_name": "天蚕土豆",
            "category_name": "玄幻",
            "chapters_count": 0,
            "cache_tags": "玄幻,热血,架空,异界大陆,巅峰,修炼,主宰",
            "words": null,
            "cover": "http://statics.zhuishushenqi.com/agent/http://image.cmfu.com/books/2750457/2750457.jpg",
            "last_parsed_at": "2017-03-28T17:24:05.000+08:00",
            "last_updated_at": "2017-03-28T17:24:05.000+08:00",
            "description": "大千世界，位面交汇，万族林立，群雄荟萃，一位位来自下位面的天之至尊，在这无尽世界，演绎着令人向往的传奇，追求着那主宰之路。 无尽火域，炎帝执掌，万火焚苍穹。 武...",
            "last_chapter": {
                "updated_at": null,
                "title": "第1496章 莫名来者"
            }

            ...
        ],
    },
    "meta": {
        "code": 10000,
        "message": "Success"
    }
}
```

返回当前榜单所有的书

### 接口

/v1/rankings/{id}

### 参数

无

### 返回

名称 | 描述
--------- | -------
data|数据信息
meta|元数据信息
id|书 ID
name|书名
author_name|作者名
category_name|分类名
chapters_count|暂时作废
cache_tags|标签
words|暂时作废
cover|封面
last_parsed_at|最后更新时间（抓取或解析）
description|书描述
last_chapter|最后章节，暂时作废
code|执行状态码，10000 为成功执行
message|执行状态说明
