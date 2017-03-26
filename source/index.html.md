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

# Cards

<a href="http://materializecss.com/cards.html">Cards</a> are a utility extracted from  <a href="http://materializecss.com/">Materialize framework </a>to display information in a new way.

You can use blue dashboard customized cards by including the blue dashboard style file in addition to thematerialize css JS file and use the cards as shown in th example.



```HTML
<!-- Materialize JS -->

<script type="text/javascript" src="assets/vendors/materialize/materialize.min.js"></script>

<!-- Basic cards -->

<div class="card info-mid">
    <div class="card-content white-text">
        <span class="card-title">Card Title</span>
        <p>
        I am a very simple card. I am good at containing small bits of information. I am convenient because I require little markup to use effectively. I am similar to what is called a panel in other frameworks.
        </p>
    </div>
    <div class="card-action">
        <a href="#" class="default-dahsboard-link">This is a link</a>
        <a href="#" class="default-dahsboard-link">This is a link</a>
    </div>
</div>

<!-- Horizontal Card -->

<div class="card horizontal">
    <div class="card-image">
        <img alt="card title" src="assets/images/card_03.jpg">
    </div>
    <div class="card-stacked">
        <div class="card-content">
            <p>I am a very simple card. I am good at containing small bits of information.</p>
        </div>
        <div class="card-action">
            <button type="button" class="btn btn-link">This is a link<button>
        </div>
    </div>
</div>
<!-- Card reveal -->

<div class="card">
    <div class="card-image">
        <img alt="card title" class="activator" src="assets/images/card_02.jpg">
    </div>
    <div class="card-content">
        <span class="card-title activator grey-text text-darken-4">Card Title<i class="material-icons right">more_vert</i></span>
        <p>I am a very simple card.</p>
    </div>
    <div class="card-action">
        <button type="button" class="btn btn-link">This is a link</button>
    </div>
    <div class="card-reveal">
        <span class="card-title grey-text text-darken-4">Card Title<i class="material-icons right">close</i></span>
        <p>Here is some more information about this product that is only revealed once clicked on.</p>
    </div>
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

