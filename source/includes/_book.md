# 图书

## 列表

```ruby

content = RestClient.get 'https://example.com/v1/books'
```

```json

{
    "data": [
        {
            "id": "mpmoms821bep",
            "name": "穿梭诸天",
            "author_name": "大日浴东海",
            "category_name": "玄幻",
            "chapters_count": 822,
            "cache_tags": "玄幻,东方玄幻",
            "words": null,
            "cover": "http://statics.zhuishushenqi.com/cover/148574333949391",
            "last_parsed_at": "2017-03-28T17:19:28.000+08:00",
            "last_updated_at": "2017-03-28T17:19:28.000+08:00",
            "description": "】 这是一个不停穿梭诸天，君临万界的故事。 风云中，他剑挑雄霸…… 小李飞刀中，他剑压江湖…… 青云山下，他看着张小凡一步步成长…… 仙剑奇侠传，他叹息一声，扭...",
            "last_chapter": {
                "updated_at": null,
                "title": "第一百三十七章 回归之惊愕（为寂寞v如雪加更）"
            }
        },
        {
            "id": "1dilvtkvvjh4g",
            "name": "异鬼记",
            "author_name": "极之光",
            "category_name": "其它",
            "chapters_count": 727,
            "cache_tags": "玄幻奇幻",
            "words": null,
            "cover": "http://statics.zhuishushenqi.com/agent/http://wap.cmread.com/r/cover_file/0252/600470252/20160115180341/cover180240.jpg",
            "last_parsed_at": "2017-03-28T17:19:28.000+08:00",
            "last_updated_at": "2017-03-28T17:19:28.000+08:00",
            "description": "一个刚刚凝结鬼体的天鬼，被迫自爆鬼元婴，重回魂魄。魂魄在快要消散的时候，进入一个被雷电击中的躯体，成为一个介乎元神与鬼魂的特殊存在。由于躯体灵根资质薄弱，又是雷...",
            "last_chapter": {
                "updated_at": null,
                "title": "第九百三十七章 答应双方交易"
            }
        },
        ...
    ],
    "meta": {
        "total_count": 151057,
        "total_pages": 6043,
        "current_page": 1,
        "last_page": false,
        "code": 10000,
        "message": "Success"
    }
}
```

返回所有的图书列表，支持分页和检索

### 接口

/v1/books

### 参数

名称 | 是否必须| 默认 | 描述
--------- | -------| ------- | -----------
name | false| | 支持模糊查询图书名称或者作者名
author_name|false||只查询作者名
page | false| 1 | 分页，当前第几页
size|false|25|每页记录数

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
total_count|累计条数
total_pages|累计页数
current_page|当前页数
last_page|是否最后一页
code|执行状态码，10000 为成功执行
message|执行状态说明


## 明细

```ruby

content = RestClient.get 'https://example.com/v1/books/1dilvtkvvjh4g'
```

```json

{
    "data": {
        "id": "1dilvtkvvjh4g",
        "name": "异鬼记",
        "author_name": "极之光",
        "category_name": "其它",
        "chapters_count": 727,
        "cache_tags": "玄幻奇幻",
        "words": null,
        "cover": "http://statics.zhuishushenqi.com/agent/http://wap.cmread.com/r/cover_file/0252/600470252/20160115180341/cover180240.jpg",
        "last_parsed_at": "2017-03-28T17:19:28.000+08:00",
        "last_updated_at": "2017-03-28T17:19:28.000+08:00",
        "description": "一个刚刚凝结鬼体的天鬼，被迫自爆鬼元婴，重回魂魄。魂魄在快要消散的时候，进入一个被雷电击中的躯体，成为一个介乎元神与鬼魂的特殊存在。由于躯体灵根资质薄弱，又是雷...",
        "last_chapter": {
            "updated_at": null,
            "title": "第九百三十七章 答应双方交易"
        }
    },
    "meta": {
        "code": 10000,
        "message": "Success"
    }
}
```

当前书的明细信息（目前内容同列表）

### 接口

/v1/books/{id}

### 参数

名称 | 是否必须| 默认 | 描述
--------- | -------| ------- | -----------
name | false| | 支持模糊查询图书名称或者作者名
author_name|false||只查询作者名
page | false| 1 | 分页，当前第几页
size|false|25|每页记录数

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


## 推荐

```ruby

content = RestClient.get 'https://example.com/v1/books/1dilvtkvvjh4g/recommended'
```

```json

{
    "data": {
        "id": "1dilvtkvvjh4g",
        "name": "异鬼记",
        "author_name": "极之光",
        "category_name": "其它",
        "chapters_count": 727,
        "cache_tags": "玄幻奇幻",
        "words": null,
        "cover": "http://statics.zhuishushenqi.com/agent/http://wap.cmread.com/r/cover_file/0252/600470252/20160115180341/cover180240.jpg",
        "last_parsed_at": "2017-03-28T17:19:28.000+08:00",
        "last_updated_at": "2017-03-28T17:19:28.000+08:00",
        "description": "一个刚刚凝结鬼体的天鬼，被迫自爆鬼元婴，重回魂魄。魂魄在快要消散的时候，进入一个被雷电击中的躯体，成为一个介乎元神与鬼魂的特殊存在。由于躯体灵根资质薄弱，又是雷...",
        "last_chapter": {
            "updated_at": null,
            "title": "第九百三十七章 答应双方交易"
        },

        ...
    },
    "meta": {
        "code": 10000,
        "message": "Success"
    }
}
```

当前书的明细信息（目前内容同列表）

### 接口

/v1/books/{id}/recommended

### 参数

名称 | 是否必须| 默认 | 描述
--------- | -------| ------- | -----------
size|false|6|推荐数量，默认6本

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



## 书源

```ruby

content = RestClient.get 'https://example.com/v1/books/1dilvtkvvjh4g/source'
```

```json

{
    "data": [
        {
            "id": "n9uvg9lruqfd",
            "book_url": "http://www.79xs.com/Html/Book/161/161888/Index.html",
            "last_chapter": "正文_第六百五十章 乌金蝰蛇偷袭",
            "chapters_count": 642,
            "last_updated_at": "2016-07-15T00:00:00.000+08:00",
            "host": "79xs.com",
            "name": "79小说网",
            "source": "shuhaha"
        },
        {
            "id": "24rpp0k4jqeqq",
            "book_url": "http://www.sanjiangge.com/book/71/71364/index.html",
            "last_chapter": "正文_第六百五十章 乌金蝰蛇偷袭",
            "chapters_count": 642,
            "last_updated_at": "2016-07-15T00:00:00.000+08:00",
            "host": "sanjiangge.com",
            "name": "三江阁",
            "source": "sanjiangge"
        },
        ...
    ],
    "meta": {
        "code": 10000,
        "message": "Success"
    }
}
```

返回当前书上有可用源的列表

### 接口

/v1/books/{id}/source

### 参数

无

### 返回

名称 | 描述
--------- | -------
data|数据信息
meta|元数据信息
id|书源 ID
book_url|书 URL
last_chapter|最后章节（目前发现追书神器的章节更新延迟比较厉害，所以可能不是最新的）
chapters_count|章节数量
last_updated_at|最后更新时间
host|源 Host
name|源网站名
source|源 Key
code|执行状态码，10000 为成功执行
message|执行状态说明
