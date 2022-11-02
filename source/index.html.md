---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - javascript

toc_footers:
  - <a href='https://user.kod.mobi'>Sign Up for a Developer Key</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Kittn API
---

# kod.mobi 
Client API (V2)

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "x-api-key: Your-Secret-Account-Token"
```

```javascript
var myHeaders = new Headers();
myHeaders.append("x-api-key", "Your-Secret-Account-Token");

var requestOptions = {
  method: 'GET',
  headers: myHeaders,
  redirect: 'follow'
};

fetch("api_endpoint_here", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

> Make sure to replace `Your-Secret-Account-Token` with your API key.

kod.mobi uses API keys to allow access to the API.

`x-api-key: Your-Secret-Account-Token`

<aside class="notice">
You must replace <code>Your-Secret-Account-Token</code> with your personal API key.
</aside>

# Message

## Create Code

```shell
curl --location --request GET 'https://api.kod.mobi/api/v2/message/create?phone=79522966236&type=telegram'
```

```javascript
var requestOptions = {
  method: 'GET',
  redirect: 'follow'
};

fetch("https://api.kod.mobi/api/v2/message/create?phone=79522966236&type=telegram", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

### HTTP Request

`GET https://api.kod.mobi/api/v2/message/create?phone=79522966236&type=telegram`

### Query Parameters

Params | Value | Default | Required
------ | ----- | ------- | --------
phone | number/номер должен начинаться с 7, +7 или 8 | - | true
type | string/in:sms,whatsapp,telegram | whatsapp(если пользователь не найден, если найден то будет выбран тот канал который он часто использует) | false
code | string | рандомный четырехзначный код | false

## Send Code

```shell
curl --location --request GET 'https://api.kod.mobi/api/v2/message/send?session_id=&type=whatsapp' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json'
```

```javascript
var myHeaders = new Headers();
myHeaders.append("Accept", "application/json");
myHeaders.append("Content-Type", "application/json");

var requestOptions = {
  method: 'GET',
  headers: myHeaders,
  redirect: 'follow'
};

fetch("https://api.kod.mobi/api/v2/message/send?session_id=&type=whatsapp", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

### HTTP Request

`GET https://api.kod.mobi/api/v2/message/send?session_id=&type=whatsapp`

### Query Parameters

Params | Value | Default | Required
------ | ----- | ------- | --------
session_id | string | - | true
type | string/in:sms,whatsapp,telegram | whatsapp(если пользователь не найден, если найден то будет выбран тот канал который он часто использует) | false
code | string | рандомный четырехзначный код | false

## Check Code

```shell
curl --location --request GET 'https://api.kod.mobi/api/v2/message/check?session_id=&code=7032' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json'
```

```javascript
var myHeaders = new Headers();
myHeaders.append("Accept", "application/json");
myHeaders.append("Content-Type", "application/json");

var requestOptions = {
  method: 'GET',
  headers: myHeaders,
  redirect: 'follow'
};

fetch("https://api.kod.mobi/api/v2/message/check?session_id=&code=7032", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

### HTTP Request

`GET https://api.kod.mobi/api/v2/message/check?session_id=&code=7032`

### Query Parameters

Params | Value | Required
------ | ----- | --------
session_id | string | true
code | string | true

# Channel

## Check Channel

```shell
curl --location --request GET 'https://api.kod.mobi/api/v2/channel/check?session_id=&type=telegram'
```

```javascript
var requestOptions = {
  method: 'GET',
  redirect: 'follow'
};

fetch("https://api.kod.mobi/api/v2/channel/check?session_id=&type=telegram", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

### HTTP Request

`GET https://api.kod.mobi/api/v2/channel/check?session_id=&type=telegram`

### Query Parameters

Params | Value | Required
------ | ----- | --------
session_id | string | true
type | string/in:sms,whatsapp,telegram | true
