---
title: API Reference

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Clarity, for Charities API
---

# Introduction

> API endpoint:
> <a href='https://giveclarity.co/'>https://giveclarity.co</a>

Welcome to the Carity, for Charities API! You can use our API endpoints to gain access to our database and.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize your requests, please follow the steps:

> Register with us as an organization.

> Get your team's API key.

> Send your API key in the header with every endpoint request.

Please use API key assigned to your team to access all the API endpoints. You can register for new API key by [Getting Started](https://giveclarity.co/users/sign_up) as an organization Or if you are already our partner, please Contact Us at `corey@giveclarity.co` to get started with our API.

Our API endoints expect for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: yourownkey`

<aside class="notice">
You must replace <code>yourownkey</code> with your personal API key.
</aside>

# Endponits

## Get All the donors for in your team

```
GET http://example.com/api/v1/donors

```

> Server will render all the donors in json format:

```json
[
  {
    "id": 2,
    "email": "test@test.com",
    "first_name": "first",
    "last_name": "donor",
    "birthday": null,
    "bio": null,
    "username": "first1",
    "avatar": "",
    "attachable_sgid": ""
  }
]
```

This endpoint retrieves all the donors.

### HTTP Request

`GET http://example.com/api/v1/donors`

### Query Parameters

No query parameter is required to pass with request.

<aside class="success">
Success — a code 200 is rendered with the data!
</aside>

## Create a donor as a team member in your Team

```
POST http://example.com/api/v1/donors

```

> Server will create a donor and render it in json format:

```json
{
  "id": 2,
  "email": "test@test.com",
  "first_name": "first",
  "last_name": "donor",
  "birthday": null,
  "bio": null,
  "username": "first1",
  "avatar": "",
  "attachable_sgid": ""
}
```

This endpoint will create a donor in your team.

### HTTP Request

`POST http://example.com/donor`

### Query Parameters

| Parameter  | Description      | Data type |
| ---------- | ---------------- | --------- |
| first_name | Donor first name | String    |
| last_name  | Donor last name  | String    |
| email      | Donor email      | String    |
| username   | Donor username   | String    |

<aside class="success">A code 200 with the data is rendered</aside>

## Get All the beneficiaries for in your team

```
GET http://example.com/api/v1/beneficiaries

```

> Server will render all the beneficiaries in json format:

```json
[
  {
    "id": 3,
    "email": "test@test.com",
    "first_name": "first",
    "last_name": "beneficiary",
    "birthday": null,
    "bio": null,
    "username": "first1",
    "avatar": "",
    "attachable_sgid": ""
  }
]
```

This endpoint retrieves all the beneficiaries.

### HTTP Request

`GET http://example.com/api/v1/beneficiaries`

### Query Parameters

No query parameter is required to pass with request.

<aside class="success">
Success — a code 200 is rendered with the data!
</aside>

## Create a beneficiary as a team member in your Team

```
POST http://example.com/api/v1/beneficiaries

```

> Server will create a beneficiary and render it in json format:

```json
{
  "id": 3,
  "email": "test@test.com",
  "first_name": "first",
  "last_name": "beneficiary",
  "user_type": "beneficiary",
  "birthday": null,
  "bio": null,
  "username": "first1",
  "avatar": "",
  "attachable_sgid": ""
}
```

This endpoint will create a beneficiary in your team.

### HTTP Request

`POST http://example.com/beneficiaries`

### Query Parameters

| Parameter  | Description            | Data type |
| ---------- | ---------------------- | --------- |
| first_name | Beneficiary first name | String    |
| last_name  | Beneficiary last name  | String    |
| email      | Beneficiary email      | String    |
| username   | Beneficiary username   | String    |

<aside class="success">A code 200 with the data is rendered</aside>

## Get All the posts of a team manager

```
GET http://example.com/api/v1/posts

```

> Server will render all the posts of a team manager in json format:

```json
[
  {
    "id": 1,
    "title": "test",
    "user_id": 1,
    "content": "test post",
    "audience": null,
    "ordered_file_ids": [],
    "files": []
  }
]
```

This endpoint retrieves all the posts by a team manager.

### HTTP Request

`GET http://example.com/api/v1/posts`

### Query Parameters

No query parameter is required to pass with request.

<aside class="success">
Success — a code 200 is rendered with the data!
</aside>

## Create a post as a team manager in your Team

```
POST http://example.com/api/v1/posts

```

> Server will create a post and render it in json format:

```json
{
  "id": 1,
  "title": "test",
  "user_id": 1,
  "content": "test post",
  "audience": null,
  "ordered_file_ids": [],
  "files": []
}
```

This endpoint will create a post by team manager in your team.

### HTTP Request

`POST http://example.com/api/v1/posts`

### Query Parameters

| Parameter  | Description            | Data type |
| ---------- | ---------------------- | --------- |
| first_name | Beneficiary first name | String    |
| last_name  | Beneficiary last name  | String    |
| email      | Beneficiary email      | String    |
| username   | Beneficiary username   | String    |

<aside class="success">A code 200 with the data is rendered</aside>

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require("kittn");

let api = kittn.authorize("meowmeowmeow");
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted": ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

| Parameter | Description                    |
| --------- | ------------------------------ |
| ID        | The ID of the kitten to delete |
