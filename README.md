<div align="left">
  <a href="https://github.com/juanroldan1989/movie_quotes">
    <img width="136" src="https://github.com/juanroldan1989/movie-quotes-api/raw/master/source/images/icon3.png" alt="movie_quotes ruby logo" />
    <img width="136" src="https://github.com/juanroldan1989/movie-quotes-api/raw/master/source/images/plus-logo.jpg" alt="ionic_movie_quoteslogo" />
    <img src="https://github.com/juanroldan1989/movie-quotes-api/raw/master/source/images/logo-slate.png" alt="Slate: API Documentation Generator" width="226">
  </a>
</div>

# MovieQuotes API Docs

* Please check all available information [here](http://juanroldan.com.ar/movie-quotes-api)

* MovieQuotes website [here](https://movie-quotes-app.herokuapp.com/)

* Big ruby fan? We've got your back with this [awesome gem](https://github.com/juanroldan1989/movie_quotes) to interact with our API

--------------------------------------------------------

This API Documentation site was built with **Slate**.

Getting Started with Slate
------------------------------

### Prerequisites

You're going to need:

 - **Linux or OS X** — Windows may work, but is unsupported.
 - **Ruby, version 2.3.1 or newer**
 - **Bundler** — If Ruby is already installed, but the `bundle` command doesn't work, just run `gem install bundler` in a terminal.

### Getting Set Up

1. Fork this repository on GitHub.
2. Clone *your forked repository* (not our original one) to your hard drive with `git clone https://github.com/YOURUSERNAME/slate.git`
3. `cd slate`
4. Initialize and start Slate. You can either do this locally, or with Vagrant:

```shell
# either run this to run locally
bundle install
bundle exec middleman server

# OR run this to run with vagrant
vagrant up
```

You can now see the docs at http://localhost:4567. Whoa! That was fast!

Now that Slate is all set up on your machine, you'll probably want to learn more about [editing Slate markdown](https://github.com/lord/slate/wiki/Markdown-Syntax), or [how to publish your docs](https://github.com/lord/slate/wiki/Deploying-Slate).

If you'd prefer to use Docker, instructions are available [in the wiki](https://github.com/lord/slate/wiki/Docker).

### Publishing your API documentation couldn't be more simple.

 1. Make sure you're working on a fork in your own account, not our original repo: `git remote show origin`.
 1. Commit your changes to the markdown source: `git commit -a -m "Update index.md"`
 2. Push the *markdown source* changes to GitHub: `git push`
 3. Run `./deploy.sh`
 4. **Friendly reminder**: Any kind of work should be done on `master` branch. Make sure `master` and `gh-pages` branches are always synced, because in the end the content published in the server is the one from `gh-pages` branch. If things are not looking as expected after deploying, feel free to remove `gh-pages` branch locally, create a fresh one from `master` and force-push it into the repository.


### Customizing Slate Them

I've applied [TradeGecko](http://developer.tradegecko.com/) styles into this project:

https://github.com/tradegecko/smaug/tree/master/source/stylesheets
