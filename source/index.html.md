---
title: API Reference for the Clarity, for Charities.

toc_footers:
  - <a href='https://giveclarity.co/' target = 'blank'>Sign Up for a Developer Key</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: API Documentation for the Clarity, for Charities API
---

# Introduction

> API endpoint:
> <a href='https://giveclarity.co/'>https://giveclarity.co</a>

Welcome to the Clarity, for Charities API Reference! You can use our API endpoints to integrate with our platform.

You can view code examples in the dark area to the right, and explore specific endpoints by selecting them from the left-side navigation menu.

# Authentication

> To authorize your requests, please follow the steps:

```
Register with us as an organization.

Get your team's API key.

Send API key in the header with every request.

```

Please use API key assigned to your team to access all the API endpoints. You can register for a new API key by [Getting Started](https://giveclarity.co/users/sign_up) as an organization. If you are already our partner, please Contact Us at `hello@giveclarity.co` to get started with the API.

Our API endoints expect for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: yourownkey`

<aside class="notice">
You must replace <code>yourownkey</code> with your personal API key.
</aside>

# Endpoints

## Get All the donors

> Server will render all the donors in json format:

```json
{
  "data": [
    {
      "id": "3758",
      "type": "donor",
      "attributes": {
        "first_name": "first",
        "last_name": "donor",
        "email": "first@donor.com",
        "time_zone": null,
        "created_at": "2023-04-05T15:56:19.626Z",
        "updated_at": "2023-04-05T15:56:19.639Z",
        "birthday": "",
        "bio": " I am first donor",
        "username": "donor1",
        "phone": null,
        "avatar": ""
      }
    }
  ]
}
```

This endpoint retrieves all the donors associated with the team.

### HTTPS Request

`GET https://giveclarity.co/api/v1/donors`

### Request Header

`Authorization header: yourownkey`

### Request Body

No request body is required to pass with request.

<aside class="success">
Success — a code 200 is rendered with the data!
</aside>

## Create a donor

> Server will create a donor and render it in json format:

```json
{
  "data": {
    "id": "3758",
    "type": "donor",
    "attributes": {
      "first_name": "first",
      "last_name": "donor",
      "email": "first@donor.com",
      "time_zone": null,
      "created_at": "2023-04-05T15:56:19.626Z",
      "updated_at": "2023-04-05T15:56:19.639Z",
      "birthday": "",
      "bio": " I am first donor",
      "username": "donor1",
      "phone": null,
      "avatar": ""
    }
  }
}
```

This endpoint will create a donor in your team.

### HTTPS Request

`POST https://giveclarity.co/api/v1/donors`

### Request Header

`Authorization header: yourownkey`

### Request Body

Please pass a FormData object in request body.

`formData(first_name: String, last_name: String, email: String, username: String, birthday: String, bio: String, avatar: Image, custom_fields: [], beneficiary_ids: [])`

<aside class="notice">
<code>custom_fields</code> should be an array of objects with  <code>team_custom_field_id</code> and <code>value</code> keys.
for example: <code>custom_fields: [{"team_custom_field_id": 1, "value": "test"}]</code>
</aside>

<aside class="notice">
<code>beneficiary_ids</code> are used to create sponsorships. It should be an array of ids of beneficairies. for example: <code> beneficiary_ids: [1, 2]</code>
</aside>

<aside class="success">A code 200 with the data is rendered</aside>

## Get All the beneficiaries

> Server will render all the beneficiaries in json format:

```json
{
  "data": [
    {
      "id": "3812",
      "type": "beneficiary",
      "attributes": {
        "first_name": "first",
        "last_name": "beneficiary",
        "email": "test@test.com",
        "time_zone": null,
        "created_at": "2023-04-06T23:48:44.277Z",
        "updated_at": "2023-04-06T23:48:44.312Z",
        "birthday": "2023-03-14",
        "bio": "first test beneficiary",
        "username": "first1",
        "phone": null,
        "avatar": ""
      }
    }
  ]
}
```

This endpoint retrieves all the beneficiaries associated with the team.

### HTTPS Request

`GET https://giveclarity.co/api/v1/beneficiaries`

### Request Header

`Authorization header: yourownkey`

### Request Body

No request body is required to pass with request.

<aside class="success">
Success — a code 200 is rendered with the data!
</aside>

## Create a beneficiary

> Server will create a beneficiary and render it in json format:

```json
{
  "data": {
    "id": "3813",
    "type": "beneficiary",
    "attributes": {
      "first_name": "first",
      "last_name": "beneficiary",
      "email": "test@test.com",
      "time_zone": null,
      "created_at": "2023-04-07T00:24:59.163Z",
      "updated_at": "2023-04-07T00:24:59.198Z",
      "birthday": "2023-03-14",
      "bio": "first test beneficiary",
      "username": "first1",
      "phone": null,
      "avatar": ""
    }
  }
}
```

This endpoint will create a beneficiary in your team.

### HTTPS Request

`POST https://giveclarity.co/api/v1/beneficiaries`

### Request Header

`Authorization header: yourownkey`

### Request Body

Please pass a FormData object in request body.

`formData(first_name: String, last_name: String, email: String, username: String, birthday: String, bio: String, avatar: Image, custom_fields: [])`

<aside class="notice">
<code>custom_fields</code> should be an array of objects with  <code>team_custom_field_id</code> and <code>value</code> keys.
for example: <code>custom_fields: [{"team_custom_field_id": 1, "value": "test"}]</code>
</aside>

<aside class="success">A code 200 with the data is rendered</aside>

## Get All the posts of a team manager

> Server will render all the posts of a team manager in json format:

```json
[
  {
    "id": 1,
    "title": "first post",
    "user_id": 1,
    "created_at": "2023-04-07T01:13:07.776Z",
    "updated_at": "2023-04-07T01:13:07.786Z",
    "content": "This is a first post by manager",
    "approved_at": "2023-04-07T01:13:07.776Z",
    "approved_by": null,
    "published_at": "2023-05-01T00:00:00.000Z",
    "audience": 0,
    "preview_images": [],
    "audience_members_count": 3,
    "ordered_file_ids": [],
    "files": [""]
  }
]
```

This endpoint retrieves all the posts by a team manager.

### HTTPS Request

`GET https://giveclarity.co/api/v1/posts`

### Request Header

`Authorization header: yourownkey`

### Request Body

No request body is required to pass with request.

<aside class="success">
Success — a code 200 is rendered with the data!
</aside>

## Create a post as a team manager, for a donor or beneficiary.

> Server will create a post and render it in json format:

```json
{
  "id": 1,
  "title": "first post",
  "user_id": 1,
  "created_at": "2023-04-07T01:13:07.776Z",
  "updated_at": "2023-04-07T01:13:07.786Z",
  "content": "This is a first post by manager",
  "approved_at": "2023-04-07T01:13:07.776Z",
  "approved_by": null,
  "published_at": "2023-05-01T00:00:00.000Z",
  "audience": 0,
  "preview_images": [],
  "audience_members_count": 3,
  "ordered_file_ids": [],
  "files": []
}
```

This endpoint will create a post by team manager as a manager, a donor, or a beneficiary in your team.

### HTTPS Request

`POST https://giveclarity.co/api/v1/posts`

### Request Header

`Authorization header: yourownkey`

### Request Body

Please pass a FormData object in request body.

`formData(user_id: INT, title: String, content: String, published_at: Date as string, audience: [], files[]: [])`

<aside class="notice">
<code>audience</code> is an array of objects where every object's key is  <code>id</code>of targeted audience.
for example: <code>audience: [{"id": "donors"}, {"id": "beneficiaries"}, {"id": "1"}]</code>
</aside>

<aside class="notice">
<code>user_id</code> is an id of the user who is creating post. User can be a manager, a donor or a beneficiary.
</aside>

<aside class="success">A code 200 with the data is rendered</aside>

## Email invite to a user.

> Server will trigger an email invite to a user:

```json
{
  "notice": "Invite sent successfully"
}
```

This endpoint will send an email invite to a user with a link to join your team.

### HTTPS Request

`POST https://giveclarity.co/api/v1/invites`

### Request Header

`Authorization header: yourownkey`

### Request Body

Please pass a JSON object in request body.

`{"user_id": INT, "message": STRING}`

<aside class="notice">
<code>user_id</code> is the id of a user.
for example: <code>{"user_id": 1, "message": "let's join!"}</code>
</aside>

<aside class="success">A code 200 with the data is rendered</aside>

## Create a Custom field.

> Server will render all custom fields of a team in JSON format:

```json
[
  {
    "id": 1,
    "team_id": 5,
    "name": "first donor field",
    "value_type": "text",
    "record_type": "donor",
    "system_key": "first donor field",
    "editable": true,
    "visible": true,
    "system_owned": false,
    "created_at": "2023-04-07T02:06:08.811Z",
    "updated_at": "2023-04-07T02:06:08.811Z",
    "friendly_name": "Text"
  }
]
```

This endpoint will create a custom field for donors, beneficiaries, or sponsorships.

### HTTPS Request

`PATCH https://giveclarity.co/api/v1/custom_fields`

### Request Header

`Authorization header: yourownkey`

### Request Body

Please pass a JSON object in request body.

`{"name": STRING, "value_type": TEXT, LONG TEXT, DATE OR LINK, "record_type": STRING, "editable": boolean, "visible": boolean}`

<aside class="notice">
for example: <code>{"name": "first donor field", "value_type": "text", "record_type": "donor",
"editable": true, "visible": true}</code>
</aside>

<aside class="success">A code 200 with the data is rendered</aside>

## Delete a Custom field.

> Server will trigger an email invite to a user:

```json
  "notice": "Custom field is deleted!"
```

This endpoint will delete a custom field if it's not a default custom field.

### HTTPS Request

`DELETE https://giveclarity.co/api/v1/custom_fields`

### Request Header

`Authorization header: yourownkey`

### Request Body

Please pass a JSON object in request body.

`{"id": INT, "record_type": STRING}`

<aside class="notice">
for example: <code>{"id": 10, "record_type": "donor"}</code>
</aside>

<aside class="success">A code 200 with the data is rendered</aside>
