# 用户

## 发送验证码

```ruby

content = RestClient.post '/v1/users/send_code'， {mobile: '1891790000'}
```

```json

{
  "meta": {
    "code": 10000,
    "message": "Success"
  }
}
```

用户在注册和找回密码之前必须通过手机验证，验证码30分钟有效。

### 接口

POST /v1/users/send_code

### 参数

名称 | 必须| 默认 | 描述
--------- | -------| ------- | -----------
mobile | true|  | 手机号码

### 返回

名称 | 描述
--------- | -------
data|数据信息
meta|元数据信息


## 验证并注册


```ruby

content = RestClient.post '/v1/users/signup'， {code: '1234', mobile: '1891790000'}
```

```json

{
  "meta": {
    "code": 10000,
    "message": "Success"
  }
}
```

使用受到的验证码进行注册。如果手机号码已经存在，则会更新资料，其他资料目前全部可选。（偷懒将接口合并到一起了）


### 接口

POST /v1/users/signup

### 参数

名称 | 必须| 默认 | 描述
--------- | -------| ------- | -----------
code | true|  | 验证码
mobile | true|  | 手机号码
email|false||邮箱
name|false||用户名
gender|false||性别，1 => 男, 2 => 女
password|false||密码

### 返回

名称 | 描述
--------- | -------
data|数据信息
meta|元数据信息