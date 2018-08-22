---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby

toc_footers:
  - <a href='https://github.com/juanroldan1989/movie_quotes#1-usage'>Sign Up for a Developer API Key</a>

includes:
  - examples
  - rate_limit
  - errors

search: true
---

# Introduction

Welcome to the <a href="http://movie-quotes-app.herokuapp.com" target="_blank">MovieQuotes</a> API! You can use this API to access well known quotes from more than **500 movies**.

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

<a href="http://movie-quotes-app.herokuapp.com" target="_blank">MovieQuotes</a> uses an API key to allow access to the API. Before anything you should get an API Key (free).

Please send an email to <a href="http://juanroldan.com.ar" target="_blank">juanroldan1989@gmail.com</a>

<a href="http://movie-quotes-app.herokuapp.com" target="_blank">MovieQuotes</a> expects for the API key to be included in **all** API requests in a header that looks like this:

`Authorization: Token token=abcd1234`

## Ruby SDK
Big ruby fan? We've got your back. There's an awesome ruby gem available to play with MovieQuote's API.

Check it out on Github: <a href='https://github.com/juanroldan1989/movie_quotes' target='_blank'>MovieQuotes</a>

# Quotes

## Membership plans

<a href="http://movie-quotes-app.herokuapp.com" target="_blank">MovieQuotes</a> API supports **3** membership plans:

Plan    | Price        | Description
------- | ------------ | -----------
Free    | $ 0          | API provides 300 quotes. Technical support on weekends.
Basic   | $ 4 / Month  | API provides 550 quotes. 24/7 technical support.
Premium | $ 7 / Month  | API provides 1000 quotes. Access to brand new quotes monthly. 24/7 technical support.

## Pagination

<a href="http://movie-quotes-app.herokuapp.com" target="_blank">MovieQuotes</a> API enables pagination via page query parameter on GET requests.

Every API call retrieves **20** quotes at a time (per page).

```ruby
require 'movie_quotes'

filter = MovieQuotes.new

filter.by_page(1)
# or
filter.by_page("1")

# Make API call
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

### HTTP Request

`GET http://movie-quotes-app.herokuapp.com/api/v1/quotes?page=1`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
page | 1 | Used to retrieve **20** quotes top on each request.


# Filters

All API methods are **chainable**, they can be applied one after another to conform the desired request.

## By Actor

```ruby
# apply "slug" format to search terms, results will be more accurate
filter.by_actor("keanu-reeves")

# Make API call
filter.results
```

```shell
# apply "slug" format to search terms, results will be more accurate
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?actor=keanu-reeves"
  -H "Authorization: Token token=abcd1234"
```

### HTTP Request

`GET http://movie-quotes-app.herokuapp.com/api/v1/quotes?actor=keanu-reeves`

### Query Parameters

Parameter | Description
--------- | -----------
actor | Used to retrieve quotes said by an actor.



## By Category (movie genre)

Categories available to query and find amazing quotes:

<table>
  <tbody>
    <tr>
      <td>action</td>
      <td>adventure</td>
      <td>animation</td>
      <td>biography</td>
      <td>comedy</td>
      <td>crime</td>
      <td>documentary</td>
    </tr>
    <tr>
      <td>drama</td>
      <td>family</td>
      <td>fantasy</td>
      <td>film-noir</td>
      <td>history</td>
      <td>horror</td>
      <td>music</td>
    </tr>
    <tr>
      <td>musical</td>
      <td>mystery</td>
      <td>romance</td>
      <td>sci-fi</td>
      <td>short</td>
      <td>sport</td>
      <td>thriller</td>
    </tr>
    <tr>
      <td>war</td>
      <td>western</td>
    </tr>
  </tbody>
</table>

```ruby
filter.by_category("action")

# "OR" behavior when multiple categories are applied
filter.by_category(["action", "crime", "drama"])

# Make API call
filter.results
```

```shell
# Single category applied
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?category=action"
  -H "Authorization: Token token=abcd1234"

# Multiples categories applied
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?categories[]=sci-fi,action"
  -H "Authorization: Token token=abcd1234"
```

### HTTP Request

`GET http://movie-quotes-app.herokuapp.com/api/v1/quotes?category=action`

### Query Parameters

Parameter | Description
--------- | -----------
category | Used to retrieve quotes said in movies from 1 or N categories.




## By Character
```ruby
filter.by_character("morpheus")

# Make API call
filter.results
```

```shell
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?character=morpheus"
  -H "Authorization: Token token=abcd1234"
```

### HTTP Request

`GET http://movie-quotes-app.herokuapp.com/api/v1/quotes?character=morpheus`

### Query Parameters

Parameter | Description
--------- | -----------
character | Used to retrieve quotes said by a character.





## By Content
```ruby
filter.by_content("spoon")

# Make API call
filter.results
```

```shell
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?content=spoon"
  -H "Authorization: Token token=abcd1234"
```

### HTTP Request

`GET http://movie-quotes-app.herokuapp.com/api/v1/quotes?content=spoon`

### Query Parameters

Parameter | Description
--------- | -----------
content | Used to retrieve quotes containing a word or pieces of quotes.





## By Movie
```ruby
# apply "slug" format to search terms, results will be more accurate
filter.by_movie("the-matrix")

# Make API call
filter.results
```

```shell
# apply "slug" format to search terms, results will be more accurate
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?movie=the-matrix"
  -H "Authorization: Token token=abcd1234"
```

### HTTP Request

`GET http://movie-quotes-app.herokuapp.com/api/v1/quotes?movie=the-matrix`

### Query Parameters

Parameter | Description
--------- | -----------
movie | Used to retrieve quotes said in a movie.





## By Multiple

Allows to query by **several filters at once** (quote's content, movie, actor, character and categories) providing only a string.

Search results are gathered following an **OR** behavior.

```ruby
filter.by_multiple("take")

# Make API call
filter.results
```

```shell
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?multiple=take"
  -H "Authorization: Token token=abcd1234"
```

### HTTP Request

`GET http://movie-quotes-app.herokuapp.com/api/v1/quotes?multiple=take`

### Query Parameters

Parameter | Description
--------- | -----------
multiple | Used to retrieve quotes which contain the word **take** on their `content` OR `movie` title OR `actor` name OR `character` name OR `categories` list





## By Rating
Quotes filtered by rating from **1(worst)** to **10(best)**.

```ruby
filter.by_rating(10)
# or
filter.by_rating("10")

# Make API call
filter.results
```

```shell
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?rating=10"
  -H "Authorization: Token token=abcd1234"
```

### HTTP Request

`GET http://movie-quotes-app.herokuapp.com/api/v1/quotes?rating=10`

### Query Parameters

Parameter | Description
--------- | -----------
rating | Used to retrieve quotes with a certain rating.





## By Year
```ruby
filter.by_year(1999)

# "OR" behavior when multiple years are applied
filter.by_year([1999, 2005])

# "OR" behavior when multiple years are applied
filter.by_year(["1999", "2005"])

# Make API call
filter.results
```

```shell
# Single year applied
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?years=1999"
  -H "Authorization: Token token=abcd1234"

# Multiples years applied
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?years[]=1999,2005"
  -H "Authorization: Token token=abcd1234"
```

### HTTP Request

`GET http://movie-quotes-app.herokuapp.com/api/v1/quotes?years=1999`

### Query Parameters

Parameter | Description
--------- | -----------
years | Used to retrieve quotes said in movies from an specific year.




## Randomly

One or many quotes can be picked randomly and returned to the client.

```ruby
# A single quote is picked randomly and returned to client.
filter.by_random

# or 
# A single quote is picked randomly and returned to client.
filter.by_random(1)
filter.by_random("1")

# or
# Four quotes are picked randomly and returned to client.
filter.by_random(4)
filter.by_random("4")

# Make API call
filter.results
```

```shell
# A single quote is picked randomly and returned to client.
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?random=1"
  -H "Authorization: Token token=abcd1234"

# Four quotes are picked randomly and returned to client.
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?random=4"
  -H "Authorization: Token token=abcd1234"
```

### HTTP Request

`GET http://movie-quotes-app.herokuapp.com/api/v1/quotes?random=4`

### Query Parameters

Parameter | Description
--------- | -----------
random | Used to retrieve 1 or N quotes randomly.
