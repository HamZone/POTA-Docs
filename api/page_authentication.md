---
layout: default
title: 身份验证
parent: 公共 API
nav_order: 20
permalink: /api/authentication.html
nav_exclude: true
search_exclude: true
---

# 身份验证
为了方便想与空中公园 API 交互的应用程序，我们已经实现了基于API密钥的身份验证。

在向空中公园 API 发送身份验证请求前需要两个密钥：
* `Application Key` - 发送给应用程序开发者
* `API Key` - 发送给用户

若要使用 API 发送已验证的请求，应用程序必须：
1. 由空中公园发送一个 `Application Key`
2. 从用户那里获取一个 `API Key`
3. 用你的 `Application Key` 来获取一个 `Session Key`
4. 用 `Session Key` 和 `API Key` 来生成一个 `Request Key`
5. 发送包含上一步生成的 `Request Key` 的 HTTP 请求</code>


## 滥用、隐私，和跟踪
空中公园可选择撤回任何用于被感知到滥用 API 的 `Application Key`

空中公园可能会因滥用或隐私问题而拒绝或限制任何开发者或用户访问 API。

空中公园不允许在包含任何形式第三方跟踪的应用程序中使用 API。


## Application Key
若要申请 `Application Key` ，请发送邮件至 <a href="mailto:help@parksontheair.com">help@parksontheair.com</a> 并在邮件中提供以下信息：
* 您的呼号（或全名）
* 有效的邮件地址
* 应用程序名称或用途（“个人使用”是一个有效的用途）

`Application Key` 将免费发给任何应用程序开发者或用户。


## API Key
用户可以通过访问他们的账户页面来生成 `API Key`。 用户必须手动生成并向应用程序提供 `API Key`。 [链接到生成并提供 API Key 所需的步骤。]

### API Key 格式
API Key 被 ASCII 句点（`.`）分隔成两部分。 第一部分被称为 `prefix`，第二部分被称为 `auth-key`。
> &lt;prefix>.&lt;auth-key>

#### 示例 Key
> oi7za94t.qz0mtfksu8sexfqt


## Session Key
可以通过使用你的 `Application Key` 向 `/session` 终结点发送未认证的 GET请求， 从而在 API 中获取到`Session Key` 。 返回的 `Session Key` 是一个由随机字母和数字组成的短 ASCII 字符串

> https://api.pota.app/session/&lt;application-key>

### API 响应码
* 200 - 成功；`Session Key` 作为响应内容返回
* 403 - 无效 `Application Key` 或 `Application Key` 已被吊销
* 500 - 发送会话时出现错误；请稍后再试

### 会话持续时间
`Session Key` 将在最后一次使用后 1 小时过期。 为了在应用程序闲置时保持 `Session Key` ，应用程序可向 `/session` 终结点发送额外请求，每5分钟最多一次。

会话与用户的公共 IP 地址绑定，如果用户的公共 IP 地址发生变化，将启动一个新的会话。 如果应用程序处于一个高动态的漫游环境中，用户的公共IP地址可能会迅速变化，那么应用程序应该在每次请求之前请求一个新的 `Session Key`。

此外，如果应用程序将很少发起认证请求， 在每次请求之前请求 `Session Key` 可能更加有效。


## Request Key
为了生成一个 `Request Key` ，应用程序必须将一个 API 提供的 `Session Key` 与用户提供的 `API Key` 结合起来。 应用程序会缓存生成的 `Request Key` ，因为它只会在 `Session Key` 改变时才会改变。

如果应用程序将为多个用户提出请求， `Session Key` 可能被重新使用。 但生成的 `Request Key` 将是每个用户唯一的。

### Request Key 格式
> &lt;session-key>.&lt;prefix>.&lt;**sha1(**&lt;session-key>.&lt;prefix>.&lt;auth-key>**)**>

#### 生成 Request Key 示例
```python
def generate_request_key(session_key, api_key):
    # api_key = <prefix>.<auth-key>
    (prefix, auth_key) = api_key.split('.')

    # auth_hash = sha1(<session-key>.<prefix>.<auth-key>)
    hash_input = session_key + '.' + prefix + '.' + auth_key
    auth_hash = hashlib.sha1(hash_input.encode('utf-8')).hexdigest()

    # request_key = <session-key>.<prefix>.<auth-hash>
    return session_key + '.' + prefix + '.' + auth_hash
```

#### 测试用例
```python
session_key = '4toztnck'
api_key = '005gubdi.ztv2055n3bulji1e'
request_key = generate_request_key(session_key, api_key)

expected_output = '4toztnck.005gubdi.8c287089997fdd5c6ab3ea274805e202a7eac4c3'

assert(request_key == expected_output)
```


## API 请求
当对已认证的 API 做出请求时，应用程序必须在请求中包括生成的 `Request Key`。 `Request Key` 可以在 `X-API-Key` HTTP头中提供，或作为 `api`的查询参数。
