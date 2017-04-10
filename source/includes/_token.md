# 授权

## 获取 Token

```ruby

content = RestClient.post '/v1/user_token'， {auth: {account: '账号信息', password: '密码'}}
```

```json

{
  "data": {
    "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE0OTE4OTQ1MzAsInN1YiI6MX0.q_6XIdrQEdymkTaXmVk7RqPfHhu_c1LVeDZREKgC9dA"
  },

  "meta": {
    "code": 10000,
    "message": "Success"
  }
}
```

API 使用了 JSON Web Token来授权，更多信息可参见：https://jwt.io/

根据账号和密码获取Token，注意这里的参数放在 auth 节点下的。（当前使用的这个 Gem 居然 hard code了，无法配置，暂且先用着）

### 接口

POST /v1/user_token

### 参数

名称 | 必须| 默认 | 描述
--------- | -------| ------- | -----------
auth[account] | true|  | 个人账号，支持手机，邮箱或者用户名
auth[password]| true | | 密码

### 返回

名称 | 描述
--------- | -------
data|数据信息
meta|元数据信息
token|返回的Token


## 验证授权


```ruby
curl -X POST -H "Authorization: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE0OTE4OTQ1MzAsInN1YiI6MX0.q_6XIdrQEdymkTaXmVk7RqPfHhu_c1LVeDZREKgC9dA" http://example.com/v1/users/1

或者


curl -X POST http://example.com/v1/users/1?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE0OTE4OTQ1MzAsInN1YiI6MX0.q_6XIdrQEdymkTaXmVk7RqPfHhu_c1LVeDZREKgC9dA
```

在请求受限接口时，请将返回的 Token 放置 Header 或者参数 token 中即可，推荐放在 Header 中



## 测试验证


```ruby

content = RestClient.get '/v1/users/profile'， {Authorization: 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE0OTE4OTQ1MzAsInN1YiI6MX0.q_6XIdrQEdymkTaXmVk7RqPfHhu_c1LVeDZREKgC9dA'}
```

```json

{
  "data": {
    "name": null,
    "mobile": "1891790000",
    "email": null,
    "sign_in_count": 1,
    "current_sign_in_at": "2017-04-10T16:12:19.000+08:00",
    "last_sign_in_at": "2017-04-10T16:12:19.000+08:00"
  },
  "meta": {
    "code": 10000,
    "message": "Success"
  }
}
```


注意，此参数Authorization是放在 Header 中传递的。

### 接口

GET /v1/users/profile
