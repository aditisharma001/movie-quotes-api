# Filtering examples

## Example 1

Filtering well known quotes by movies like **Die Hard** and actors like **Bruce Willis**

```ruby
# apply "slug" format to search terms, results will be more accurate
filter.by_movie("die-hard").by_actor("bruce-willis")

# Make API call
filter.results
```

```shell
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?movie=die-hard&actor=bruce-willis"
  -H "Authorization: Token token=abcd1234"
```

> The above command returns JSON structured like this:

```json
[
  {
    "content": "Yippie-ki-yay, motherfucker!",
    "rating": 5,
    "year": 1988,
    "categories": [
      "Thriller",
      "Crime",
      "Action"
    ],
    "image_large_url": "https://i.ytimg.com/vi/YfpDSNNgYhI/hqdefault.jpg",
    "image_thumb_url": "https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcRlniyMNhCV4h8UF9zn6Lka4s-OTU_j7Br43Kp5OR7eGljOAIpDXKystfQ",
    "movie": {
      "title": "Die Hard",
      "slug": "die-hard"
    },
    "character": {
      "name": "John Mc Clane",
      "slug": "john-mc-clane"
    },
    "actor": {
      "name": "Bruce Willis",
      "slug": "bruce-willis"
    }
  }
]
```

## Example 2

Filtering well known quotes by actors like **Al Pacino**


```ruby
# apply "slug" format to search terms, results will be more accurate
filter.by_actor("al-pacino")

# Make API call
filter.results
```

```shell
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?actor=al-pacino"
  -H "Authorization: Token token=abcd1234"
```

> The above command returns JSON structured like this:

```json
[
  {
    "content":"Keep your friends close, but your enemies closer.",
    "rating": 5,
    "year":1974,
    "categories":[
      "Crime",
      "Drama"
    ],
    "image_large_url":"https://i.ytimg.com/vi/DfHJDLoGInM/hqdefault.jpg",
    "image_thumb_url":"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQHyFYb7t8Qoniyea8IlFDvte0hvB8wzPBQWenC8hV_oMUudfiWlAzDEXgW",
    "movie":{
      "title":"The Godfather Part Ii",
      "slug":"the-godfather-part-ii"
    },
    "character":{
      "name":"Michael Corleone",
      "slug":"michael-corleone"
    },
    "actor":{
      "name":"Al Pacino",
      "slug":"al-pacino"
    }
  },
  {
    "content":"Say 'hello' to my little friend!",
    "rating": 5,
    "year":1983,
    "categories":[
      "Crime",
      "Drama"
    ],
    "image_large_url":"https://i.ytimg.com/vi/a_z4IuxAqpE/maxresdefault.jpg",
    "image_thumb_url":"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRiQEnHHPSvib02Te1fLCBaEyzMlkpK1Fomc7wFwu0lt6FZxv-gUavr6XeA",
    "movie":{
      "title":"Scarface",
      "slug":"scarface"
    },
    "character":{
      "name":"Tony Montana",
      "slug":"tony-montana"
    },
    "actor":{
      "name":"Al Pacino",
      "slug":"al-pacino"
    }
  },
  ...
]
```

## Example 3

Filtering well known quotes by movie categories like **crime** & **drama** and years **1976** & **1991**

```ruby
filter.by_category(["crime", "drama"]).by_year([1976, 1991])

# Make API call
filter.results
```

```shell
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?categories[]=crime,drama&years[]=1976,1991"
  -H "Authorization: Token token=abcd1234"
```

> The above command returns JSON structured like this:

```json
[
  {
    "content":"You talkin' to me?",
    "rating": 5,
    "year":1976,
    "categories":[
      "Crime",
      "Drama"
    ],
    "image_large_url":"https://i.ytimg.com/vi/-QWL-FwX4t4/maxresdefault.jpg",
    "image_thumb_url":"https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcQsrFYpPUa_qLZqvjL53JrBsWSLlfYBaC5qiXdNhDSTZZysA2U_IaK03HG3",
    "movie":{
      "title":"Taxi Driver",
      "slug":"taxi-driver"
    },
    "character":{
      "name":"Travis Bickle",
      "slug":"travis-bickle"
    },
    "actor":{
      "name":"Robert De Niro",
      "slug":"robert-de-niro"
    }
  },
  {
    "content":"A census taker once tried to test me. I ate his liver with some fava beans and a nice Chianti.",
    "rating": 5,
    "year":1991,
    "categories":[
      "Thriller",
      "Crime",
      "Drama"
    ],
    "image_large_url":"https://i.ytimg.com/vi/M1b2v_Lls3A/maxresdefault.jpg",
    "image_thumb_url":"https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcQO6iO860KO8e6Qmuv_ogCKdHXdo5CgWpPioU6CF9g5FSoqbQNoXPccQJo",
    "movie":{
      "title":"The Silence Of The Lambs",
      "slug":"the-silence-of-the-lambs"
    },
    "character":{
      "name":"Dr. Hannibal Lecter",
      "slug":"dr-hannibal-lecter"
    },
    "actor":{
      "name":"Anthony Hopkins",
      "slug":"anthony-hopkins"
    }
  },
  {
    "content":"I do wish we could chat longer, but I'm having an old friend for dinner.",
    "rating": 5,
    "year":1991,
    "categories":[
      "Thriller",
      "Crime",
      "Drama"
    ],
    "image_large_url":"https://i.ytimg.com/vi/sbJ89LFheTs/maxresdefault.jpg",
    "image_thumb_url":"https://encrypted-tbn2.gstatic.com/images?q=tbn:ANd9GcRnGtsUwpoCc-5nw_zznRS2615ZafAiESSebcMbC9NoT83Mh5XvnEI0ohg",
    "movie":{
      "title":"The Silence Of The Lambs",
      "slug":"the-silence-of-the-lambs"
    },
    "character":{
      "name":"Dr. Hannibal Lecter",
      "slug":"dr-hannibal-lecter"
    },
    "actor":{
      "name":"Anthony Hopkins",
      "slug":"anthony-hopkins"
    }
  },
  {
    "content":"I'm as mad as hell, and I'm not going to take this anymore!",
    "rating": 5,
    "year":1976,
    "categories":[
      "Biography",
      "Drama"
    ],
    "image_large_url":"https://i.ytimg.com/vi/ZwMVMbmQBug/maxresdefault.jpg",
    "image_thumb_url":"https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcTsFCb5V4pS0taLWJwiZTDhZXD_qzzVgtmALirHoHLbicudOGFuZew-ujhH",
    "movie":{
      "title":"Network",
      "slug":"network"
    },
    "character":{
      "name":"Howard Beale",
      "slug":"howard-beale"
    },
    "actor":{
      "name":"Peter Finch",
      "slug":"peter-finch"
    }
  },
  {
    "content":"Yo, Adrian!",
    "rating": 5,
    "year":1976,
    "categories":[
      "Sport",
      "Drama"
    ],
    "image_large_url":"https://i.ytimg.com/vi/WgScBiXkO9Y/hqdefault.jpg",
    "image_thumb_url":"https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcQF_Rd6Z3208kVy83_1LvvJsXUme4XMVQkejNadWsF4DzbIbgcyL-Z0rP4",
    "movie":{
      "title":"Rocky",
      "slug":"rocky"
    },
    "character":{
      "name":"Rocky Balboa",
      "slug":"rocky-balboa"
    },
    "actor":{
      "name":"Sylvester Stallone",
      "slug":"sylvester-stallone"
    }
  },
  ...
]
```

## Example 4

Filtering well known quotes by characters like **Harry Callahan**

```ruby
# apply "slug" format to search terms, results will be more accurate
filter.by_character("harry-callahan")

# Make API call
filter.results
```

```shell
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?character=harry-callahan"
  -H "Authorization: Token token=abcd1234"
```

> The above command returns JSON structured like this:

```json
[
  {
    "content":"Go ahead, make my day.",
    "rating": 5,
    "year":1983,
    "categories":[
      "Thriller",
      "Action"
    ],
    "image_large_url":"https://i.ytimg.com/vi/n_SU-cJFRjs/hqdefault.jpg",
    "image_thumb_url":"https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcQn33w-E743mL3L-ar6uI9vzE9Nu8wRE_d8UkQsDcT5vCpjWUH5TfP6szOA",
    "movie":{
      "title":"Sudden Impact",
      "slug":"sudden-impact"
    },
    "character":{
      "name":"Harry Callahan",
      "slug":"harry-callahan"
    },
    "actor":{
      "name":"Clint Eastwood",
      "slug":"clint-eastwood"
    }
  },
  {
    "content":"You've got to ask yourself one question: 'Do I feel lucky?' Well, do ya, punk?",
    "rating": 5,
    "year":1971,
    "categories":[
      "Thriller",
      "Crime",
      "Action"
    ],
    "image_large_url":"https://i.ytimg.com/vi/8Xjr2hnOHiM/maxresdefault.jpg",
    "image_thumb_url":"https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcTgtJip8s8q3PZ2O9mxmpVwMBsndKmFKAVJ--Oca1b6WlznU8BpTUD-Xg4",
    "movie":{
      "title":"Dirty Harry",
      "slug":"dirty-harry"
    },
    "character":{
      "name":"Harry Callahan",
      "slug":"harry-callahan"
    },
    "actor":{
      "name":"Clint Eastwood",
      "slug":"clint-eastwood"
    }
  }
]
```
