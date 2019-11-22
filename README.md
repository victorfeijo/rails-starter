# Connie.social

Core codebase for https://connie.social web application.

## Requirements

In order to use and develop this application you're gonna need:

* Ruby 2.6.5
* Rails 6.0.1
* Yarn
* NodeJS
* PostgreSQL 11.5 (recommended version)
* Redis server

## Installation

Make sure that you have all the requirements fullfiled so you can proceed with the installation.

First, you need to install ruby's version 2.6.5 by using [RVM](https://rvm.io/rvm/install) or [rbenv](https://github.com/rbenv/rbenv). Example of installing with **RVM**:

```shell
rvm install 2.6.5
```

After that, make sure that your current ruby version is 2.6.5:

```
ruby --version
```

If the previous command return the correct ruby version can move to the next step.

Check if PostgreSQL is running properly. Using macOSX with brew services:

```
brew services list
```

If postgresql is not with the **started** status you can simply run:

```
brew services start postgresql
```

And you should be ready to run the rails application.

Clone this repository to your workspace and install the project dependencies:

```
bundle install
```

If you don't have bundler, you can install it by running `gem install bundler`.

Install javascript dependencies with **yarn**:

```
yarn install
```

Create development and testing databases and then run the migrations:

```
rails db:create db:migrate
```

To finish you just need to boot the puma server and this is easily done by running:

```
rails s
```

After that you should be able to access the application on `http://localhost:3000/`.


### OBS

Don't forget to set your local environment variables. You can copy `.env.sample` to `.env` and then
add all the necessary variables to it.


## Gemfile

It includes application gems like:

* [Autoprefixer Rails](https://github.com/ai/autoprefixer-rails) for CSS vendor prefixes
* [Bourbon](https://github.com/thoughtbot/bourbon) for Sass mixins
* [Normalize](https://necolas.github.io/normalize.css/) for resetting browser styles
* [Oj](http://www.ohler.com/oj/) for fast json parsing
* [Rack Timeout](https://github.com/heroku/rack-timeout) to abort requests that are taking too long
* [Simple Form](https://github.com/plataformatec/simple_form) for form markup and style
* [Sidekiq](https://github.com/mperham/sidekiq) for async job processing

And development gems like:

* [Dotenv](https://github.com/bkeepers/dotenv) for loading environment variables
* [Pry Rails](https://github.com/rweng/pry-rails) for interactively exploring objects
* [Bullet](https://github.com/flyerhzm/bullet) for help to kill N+1 queries and unused eager loading
* [Better Errors](https://github.com/BetterErrors/better_errors) for better debugging via in-browser IRB consoles.

And testing gems like:

* [Factory Bot](https://github.com/thoughtbot/factory_bot) for test data
* [RSpec](https://github.com/rspec/rspec) for unit testing
* [RSpec Mocks](https://github.com/rspec/rspec-mocks) for stubbing and spying
* [Timecop](https://github.com/travisjeffery/timecop) for testing time

