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

# Loading

Loaders could be used in many places but two main functionalities are that they are used when the process the user is waiting for is determinate or indeterminate.

* Progress bars and circles are used in determinate operations.

* Loaders are used in indeterminate operations.

* Progress circles. 
  - These progress shapes were extracted from the <a href="https://kimmobrunfeldt.github.io/progressbar.js/">PROGRESS BAR.JS</a> 
  - In order to use them you need to include ProgressBar.js Javascript file. <br>
  - You can manipulate and play with the progress circle options as you like using the option provided by the library.

* Progress bars.
  - Same as the Progress circles above you should include the include ProgressBar.js Javascript file.

* Placeholder loader.
  - This famous loader is used as stand alone plugin meaning that it doesn't need any libraries, all you need to do is to include the blue dashboard Style file and use it just like the example does.

* Indeterminate loaders.
  - To use any of the indeterminate loaders all you need to do is to include the dashboard style file as before and do as the example shows.

<aside class="notice">
Please note that in blue dashboard the loaders are displayed and hidden using Jquery.
</aside>

```HTML

<!-- Progress bar.js library -->

<script type="text/javascript" src="progressbar.min.js"></script>

<!-- Progress bar-circle container -->

<div id="container"> </div>


<!-- Placeholder loader -->

<div class="timeline-item">
    <div class="animated-background facebook">
        <div class="background-masker header-top"></div>
        <div class="background-masker header-left"></div>
        <div class="background-masker header-right"></div>
        <div class="background-masker header-bottom"></div>
        <div class="background-masker subheader-left"></div>
        <div class="background-masker subheader-right"></div>
        <div class="background-masker subheader-bottom"></div>
        <div class="background-masker content-top"></div>
        <div class="background-masker content-first-end"></div>
        <div class="background-masker content-second-line"></div>
        <div class="background-masker content-second-end"></div>
        <div class="background-masker content-third-line"></div>
        <div class="background-masker content-third-end"></div>
    </div>
</div>

<!-- Indeterminate circle loader -->

<div class="loader1">
    <svg class="circular" viewBox="25 25 50 50">
        <circle class="path" cx="50" cy="50" r="20" fill="none" stroke-width="2" stroke-miterlimit="10" />
    </svg>
</div>

<!-- Indeterminate bar loader -->

<div class="loader"></div>

<!-- Indeterminate cube loader -->
<div id="loader" class="vertical--center">
    <div class="vertical-center__element">
        <span class="preloader preloader--top"></span>
        <span class="preloader preloader--bottom"></span>
    </div>
</div>

```

```javascript

// Progress circle initialization 

var bar = new ProgressBar.Circle(container, {
  strokeWidth: 6,
  easing: 'easeInOut',
  duration: 1400,
  color: '#FFEA82',
  trailColor: '#eee',
  trailWidth: 1,
  svgStyle: null
});

bar.animate(1.0);

// Progress bar initialization 

var bar = new ProgressBar.Line(container, {
  strokeWidth: 4,
  easing: 'easeInOut',
  duration: 1400,
  color: '#FFEA82',
  trailColor: '#eee',
  trailWidth: 1,
  svgStyle: {width: '100%', height: '100%'}
});

bar.animate(1.0);
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

