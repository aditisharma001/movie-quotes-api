# Filtering examples

## Example 1

Filtering well known quotes by movies like **The Matrix**

```ruby
# apply "slug" format to search terms, results will be more accurate
filter.by_movie("the-matrix")

# Make API call
filter.results
```

```shell
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?movie=the-matrix"
  -H "Authorization: Token token=abcd1234"
```

> The above command returns JSON structured like this:

```json
[
  {
    "content": "Never send a human to do a machine's job.",
    "year": 1999,
    "categories": [
      "Action",
      "Adventure",
      "Sci-Fi"
    ],
    "image_large_url": "https://i.ytimg.com/vi/xq7x1KQMjqw/maxresdefault.jpg",
    "image_thumb_url": "https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcTXQQ00AD5fSgEjG-0UP6Gj7KwZhF7_ENlaJXqM98-7gLZo_cKRSanbwyk",
    "rating": 10,
    "movie": {
      "title": "The Matrix",
      "slug": "the-matrix"
    },
    "character": {
      "name": "Agent Smith",
      "slug": "agent-smith"
    },
    "actor": {
      "name": "Hugo Weaving",
      "slug": "hugo-weaving"
    }
  },
  {
    "content": "The Matrix is the world that has been pulled over your eyes to blind you from the truth.",
    "year": 1999,
    "categories": [
      "Action",
      "Adventure",
      "Sci-Fi"
    ],
    "image_large_url": "https://i.ytimg.com/vi/O4zICmyuNvs/hqdefault.jpg",
    "image_thumb_url": "https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcTm1nJGU1MR5iWW001gqBVBPzLHpGX_rT3ioECTM3m-PPHJUntH5Xbu1OI",
    "rating": 10,
    "movie": {
      "title": "The Matrix",
      "slug": "the-matrix"
    },
    "character": {
      "name": "Morpheus",
      "slug": "morpheus"
    },
    "actor": {
      "name": "Laurence Fishburne",
      "slug": "laurence-fishburne"
    }
  },
  {
    "content": "There is no spoon.",
    "year": 1999,
    "categories": [
      "Action",
      "Adventure",
      "Sci-Fi"
    ],
    "image_large_url": "https://i.ytimg.com/vi/XO0pcWxcROI/maxresdefault.jpg",
    "image_thumb_url": "https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcRMamYtDE9kTXvKdA308D-HkaOFRZi17jxupMuL950MRLIJWGg23NFk0JUk",
    "rating": 10,
    "movie": {
      "title": "The Matrix",
      "slug": "the-matrix"
    },
    "character": {
      "name": "Spoon Boy",
      "slug": "spoon-boy"
    },
    "actor": {
      "name": "Spoon Boy",
      "slug": "spoon-boy"
    }
  },
  {
    "content": "Then you'll see, that it is not the spoon that bends, it is only yourself.",
    "year": 1999,
    "categories": [
      "Action",
      "Adventure",
      "Sci-Fi"
    ],
    "image_large_url": "https://i.ytimg.com/vi/uAXtO5dMqEI/hqdefault.jpg",
    "image_thumb_url": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSp8hmUNY_YCq0imcusA5-PDQo7-Y4a5JVpB4VIG6y9dugMYZhspZIoiGM",
    "rating": 10,
    "movie": {
      "title": "The Matrix",
      "slug": "the-matrix"
    },
    "character": {
      "name": "Spoon Boy",
      "slug": "spoon-boy"
    },
    "actor": {
      "name": "Spoon Boy",
      "slug": "spoon-boy"
    }
  },
  {
    "content": "Mr. Anderson. Surprised to see me?",
    "year": 2003,
    "categories": [
      "Action",
      "Sci-Fi"
    ],
    "image_large_url": "https://i.ytimg.com/vi/hUAie-X3u8I/hqdefault.jpg",
    "image_thumb_url": "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQN5-L0hcFyndEfAq-hU4ewoAfKMszC0Vpp357PiDHiKsDz0sB7Pz-0CkbB",
    "rating": 7,
    "movie": {
      "title": "The Matrix Reloaded ",
      "slug": "the-matrix-reloaded"
    },
    "character": {
      "name": "Agent Smith",
      "slug": "agent-smith"
    },
    "actor": {
      "name": "Hugo Weaving",
      "slug": "hugo-weaving"
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

## Example 5

Filtering quotes which contain the word **take** on their `content` OR `movie` title OR `actor` name OR `character` name OR `categories` list:

```ruby
filter.by_multiple("take")

# Make API call
filter.results
```

```shell
curl "http://movie-quotes-app.herokuapp.com/api/v1/quotes?multiple=take"
  -H "Authorization: Token token=abcd1234"
```

> The above command returns JSON structured like this:

```json
[
   {
      "content":"They may take our lives, but they'll never take our freedom!",
      "year":1995,
      "categories":[
         "Biography",
         "Drama",
         "Action"
      ],
      "image_large_url":"https://i.ytimg.com/vi/BcZ-DaRkj5g/maxresdefault.jpg",
      "image_thumb_url":"https://encrypted-tbn2.gstatic.com/images?q=tbn:ANd9GcRa7cBYH2OadLo8-D6ugY_jAYxaSmFY5lXSbuTuiKsflonMVXj7Ms4VGU8",
      "rating":10,
      "movie":{
         "title":"Braveheart",
         "slug":"braveheart"
      },
      "character":{
         "name":"William Wallace",
         "slug":"william-wallace"
      },
      "actor":{
         "name":"Mel Gibson",
         "slug":"mel-gibson"
      }
   },
   {
      "content":"A census taker once tried to test me. I ate his liver with some fava beans and a nice Chianti.",
      "year":1991,
      "categories":[
         "Thriller",
         "Crime",
         "Drama"
      ],
      "image_large_url":"https://i.ytimg.com/vi/M1b2v_Lls3A/maxresdefault.jpg",
      "image_thumb_url":"https://encrypted-tbn1.gstatic.com/images?q=tbn:ANd9GcQO6iO860KO8e6Qmuv_ogCKdHXdo5CgWpPioU6CF9g5FSoqbQNoXPccQJo",
      "rating":10,
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
      "content":"Leave the gun. Take the cannolis.",
      "year":1972,
      "categories":[
         "Crime",
         "Drama"
      ],
      "image_large_url":"https://i.ytimg.com/vi/35fLKn2Tq3o/hqdefault.jpg",
      "image_thumb_url":"https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcRaL2_UrrtdUlEX4TmLww_azWQpX4qfLDB2YYpv552S2GAqjiulzSgcnAEe",
      "rating":8,
      "movie":{
         "title":"The Godfather",
         "slug":"the-godfather"
      },
      "character":{
         "name":"Pete Clemenza",
         "slug":"pete-clemenza"
      },
      "actor":{
         "name":"Richard S. Castellano",
         "slug":"richard-s-castellano"
      }
   },
   {
      "content":"If you let my daughter go now, that'll be the end of it. I will not look for you, I will not pursue you. But if you don't, I will look for you, I will find you, and I will kill you.",
      "year":2008,
      "categories":[
         "Thriller",
         "Crime",
         "Action"
      ],
      "image_large_url":"https://cdn.meme.am/instances/36649014.jpg",
      "image_thumb_url":"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSrBlvDKjs3w_xKtiXSbdY6wSr3MUK37nGtYM5jSgxyhCI75_J-LhO3FQ",
      "rating":10,
      "movie":{
         "title":"Taken",
         "slug":"taken"
      },
      "character":{
         "name":"Bryan Mills",
         "slug":"bryan-mills"
      },
      "actor":{
         "name":"Liam Neeson",
         "slug":"liam-neeson"
      }
   }
]
```