---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='https://github.com/juanroldan1989/movie_quotes#1-usage'>Sign Up for a Developer API Key</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the **MovieQuotes** API! You can use this API to access well known quotes from more than **500 movies**.

Search through movie quotes by **actors**, **characters**, **movies**, **genres**, **years** and even **pieces** of quotes.

There are language bindings in **Shell** & **Ruby**! You can view code **examples** in the dark area to the **right** and switch the programming language of the examples with the tabs in the **top right**.

# Authentication

> Setup the API Key

```shell
# With shell, you can just pass the correct header with each request
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes"
  -H "Authorization: Token token=abcd1234"
```

```ruby
MovieQuotes.configure do |config|
  config.api_key = "abcd1234"
end

# Then create a new filter instance like this:
require 'movie_quotes'

filter = MovieQuotes.new
```

> Make sure to replace `abcd1234` with your API key

MovieQuotes uses an API key to allow access to the API. Before anything you should get an API Key (free).

Please send an email to [juanroldan1989@gmail.com](https://github.com/juanroldan1989/movie_quotes#1-usage)

MovieQuotes expects for the API key to be included in **all** API requests to the server in a header that looks like this:

`Authorization: Token token=abcd1234`

<aside class="notice">
You must replace <code>abcd1234</code> with your personal API key.
</aside>

# Quotes

## Get All Quotes

```ruby
require 'movie_quotes'

filter = MovieQuotes.new
filter.results
```

```shell
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?page=1"
  -H "Authorization: Token token=abcd1234"
```

> The above command returns JSON structured like this:

```json
[
  {
    "content": "Oh, no, it wasn't the airplanes. It was Beauty killed the Beast.",
    "year": 1933,
    "categories": ["Drama", "Action", "Adventure"],
    "image_large_url": "https://s-media-cache-ak0.pinimg.com/736x/56/9c/f2/569cf2832aaabbcaa3487f22d335b4d7.jpg",
    "image_thumb_url":"https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcSI54WEStqtfEBeocTd1umDmBV4T2-u8D4NB_EJ13PUTUdMBuwfJde4sb4",
    "rating": 8,
    "movie": {
      "title": "King Kong",
      "slug": "king-kong"
    },
    "character": {
      "name": "Carl Denham",
      "slug": "carl-denham"
    },
    "actor":{
      "name": "Robert Armstrong",
      "slug": "robert-armstrong"
    }
  },
  ...
]
```

This endpoint retrieves all quotes (default to **20** per page).

### HTTP Request

`GET http://movie-quotes-app.herokuapp.com/api/v1/quotes`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | Used to retrieve **20** quotes top on each request.


## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
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
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

