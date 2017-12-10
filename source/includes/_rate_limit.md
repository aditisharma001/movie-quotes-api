# Rate Limiting

<a href="http://movie-quotes-app.herokuapp.com" target="_blank">MovieQuotes</a> API provides a rate limit of **5** requests per **5** seconds.

If you go over this limit the API will return a response with a status code of **429** until the reset time.
