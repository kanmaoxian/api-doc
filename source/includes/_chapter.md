# 章节

## 列表

```ruby

content = RestClient.get 'https://example.com/v1/books/mpmoms821bep/chapters'
```

```json

{
    "data": [
        {
            "id": "2cn",
            "title": "第一章 融合"
        },
        {
            "id": "2co",
            "title": "第二章 风云之剑圣"
        },
        ...
    ],
    "meta": {
        "code": 10000,
        "message": "Success"
    }
}
```

返回当前源的章节，如果源为空，则返回最后更新源的章节列表

### 接口

/v1/books/{book_id}/chapters

### 参数

名称 | 必须| 默认 | 描述
--------- | -------| ------- | -----------
source | false| 最后更新的源 | 换源，加载不同源的章节，此值为 v1/books/{book_id}/source 返回中的 源ID
original| false | | 如果有传递此参数，会实时抓取源对应的章节列表
compress| false || 如果传递此参数，则会将章节打包成一个 zip 文件，包含chapters.json文件

### 返回

名称 | 描述
--------- | -------
data|数据信息
meta|元数据信息
id|章节 ID
title|章节标题
code|执行状态码，10000 为成功执行
message|执行状态说明


## 正文

```ruby

content = RestClient.get 'https://example.com/v1/books/mpmoms821bep/chapters/2cn'
```

```json

{
    "data": {
        "id": "2cn",
        "title": "第一章 融合",
        "content": "<a href=\"<br /><br />    夕阳西下，残红如血。<br /><br />    树林旁，溪流岸，碎石上一个少年猛地坐起，一阵咳嗽，吐出了几口污水。<br /><br />    “好疼！”楚阳皱紧眉头，痛苦不堪，迷糊的眼睛终于看清周围的情况，顿时一呆，“这、这是哪里？我不是刚买一个青铜门的小挂饰，..."
    },
    "meta": {
        "code": 10000,
        "message": "Success"
    }
}
```

返回正文内容（此接口为实时抓取，目前没有缓存到本地）

### 接口

/v1/books/{book_id}/chapters/{chapter_id}

### 参数

无

### 返回

名称 | 描述
--------- | -------
data|数据信息
meta|元数据信息
id|章节 ID
title|章节标题
content|章节内容
code|执行状态码，10000 为成功执行
message|执行状态说明


