#  书单

## 列表

```ruby

content = RestClient.get 'https://example.com/v1/book_lists'
```

```json

{
    "data": [
        {
            "id": "1",
            "name": "【男频强推】yy小说，无敌爽",
            "books_count": 52,
            "cover": "http://statics.zhuishushenqi.com/agent/http://rm2.kingreader.com/book/1253527%2Fm%2F%5B640%5D_%E6%9E%81%E5%93%81%E5%81%B7%E9%A6%99.jpg",
            "desc": "看到这些我只想说666，果断见识到一个个怎么都死不了的越来越吊炸天的神，是怎样炼成的！精品爽文，不喜勿喷。都市、玄幻、穿越、重生、灵异各类50+本，搜罗不易，推荐给大家，对味请左上收藏。",
            "tag": "时空,都市"
        }
    ],
    "meta": {
        "total_count": 3058,
        "total_pages": 3058,
        "current_page": 1,
        "last_page": false,
        "code": 10000,
        "message": "Success"
    }
}
```

返回分页的的书单列表

### 接口

/v1/book_lists

### 参数

名称 | 是否必须| 默认 | 描述
--------- | -------| ------- | -----------
name | false| | 书单名
page | false| 1 | 分页，当前第几页
size|false|25|每页记录数

### 返回

名称 | 描述
--------- | -------
data|数据信息
meta|元数据信息
id|书单 ID
name|书单名称
cover|书单封面
books_count|书单书量
desc|书单描述
code|执行状态码，10000 为成功执行
message|执行状态说明


## 明细

```ruby

content = RestClient.get 'https://example.com/v1/book_lists/1'
```

```json

{
    "data": [
        {
            "id": "y4vavzgs1fym",
            "name": "雪鹰领主",
            "author_name": "我吃西红柿",
            "category_name": "玄幻",
            "chapters_count": 0,
            "cache_tags": "玄幻,异世大陆",
            "words": "295.05万字",
            "cover": "http://qidian.qpic.cn/qdbimg/349573/3513193/150",
            "last_parsed_at": null,
            "last_updated_at": "2017-03-05T23:44:10.000+08:00",
            "description": "在夏族的安阳行省，有一个很小很不起眼的领地，叫——雪鹰领！故事，就从这里开始！**继《莽荒纪》《吞噬星空》《九鼎记》《盘龙》《星辰变》《寸芒》《星峰",
            "last_chapter": {
                "updated_at": null,
                "title": null
            }
        }
    ],
    "meta": {
        "code": 10000,
        "message": "Success"
    }
}
```

返回当前书单所有的书

### 接口

/v1/book_lists/{id}

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
