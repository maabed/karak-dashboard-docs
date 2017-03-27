---
title: API Reference

language_tabs:
  - HTML
  - javascript
  - CSS

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Panels

In Blue dashboard panels you can use many types of panels such as collapsing panels and full screen panels or even draggable panels.

All you need to do is to include the blue dashboard style file.


<aside class="notice">
Please note that if you want to use the drag and drop panel you need to include <a href="https://bevacqua.github.io/dragula/">Dragula</a> library in addition to the Drag and drop costume file as shown in the example.
</aside>


```HTML
<!-- Dragula library -->

`<link type="text/css" href="dragula.css" />`
`<script type="text/javascript" src="dragula.js"></script>`

<!-- Drag and drop costume file -->

`<link type="text/css" href="drag_drop.css" />`

<!-- Collapsible Panel -->

<div class="panel-group">
    <div class="panel panel-default no-borders">
        <div class="panel-heading dashboard-panel">
            Panel Heading
            <a data-toggle="collapse" data-target="#demo">
                <span class="glyphicon glyphicon-chevron-up float-right"></span>
            </a>
        </div>
        <div id="demo" class="panel-collapse collapse in">
            <div class="panel-body">
                <p>
                    Lorem Ipsum is simply dumtype setting industry. Lorem Ipstandard dummy text ever since the scrambled.
                </p>
            </div>
            <div class="panel-footer">Panel Footer</div>
        </div>
    </div>
</div>

<!-- Panels With Fullscreen -->

<div class="panel panel-default no-borders">
    <div class="panel-heading">
        Panel Heading
        <ul class="list-inline panel-actions">
            <li>
                <p id="panel-fullscreen" role="button" title="Toggle fullscreen"><i class="glyphicon glyphicon-resize-full"></i></li>
        </ul>
    </div>
    <div class="panel-body">
        <p>Lorem Ipsum is simply dummy text of the printing and typesetting 
        industry. Lorem Ipsum has been the industry's standard dummy text ever 
        since the scrambled Lorem Ipsum has been the industry's.
        </p>
    </div>
</div>

<!-- Panels With Contextual Classes -->

<div class="panel panel-primary">
    <div class="panel-heading primary-mid">Panel with panel-primary class</div>
    <div class="panel-body">Panel Content</div>
</div>

```


# Authentication

> To authorize, use this code:

```HTML
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```javascript
import kittn

api = kittn.authorize('meowmeowmeow')
```

```CSS
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```


> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```HTML
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```javascript
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```CSS
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```HTML
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```javascript
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```CSS
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```


> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

