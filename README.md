# Rails 5 / React / Webpacker boilerplate
.. A very minimalistic one.

[![CircleCI](https://circleci.com/gh/artemv/rails-react-webpacker-boilerplate.svg?style=svg)](https://circleci.com/gh/artemv/rails-react-webpacker-boilerplate)

## Pre-requisites
* Ruby 2.4.1
* PostgreSQL 9.4.4
* yarn
* node > 7.10.1

## Run the app locally

After you got pre-requisites installed you should be able to install the dependencies by running
```
bundle install
yarn --frozen-lockfile
```

Create and initilize the database with:
```
rake db:setup
rake db:seed
```

### Start

```
bundle exec guard start --no-interactions
```

This will:

 * start local Rails server on port 3000
 * start the Webpacker dev server
 * monitor files changes and run [rubocop](docs/rubocop.md) inspections on changes
 * run bundle install when needed

### Test users

Use a@b.de/foobar to log in.
 
### Run the tests

This app is tested using *RSpec* and *Mocha*/*Enzyme*. To run all tests (residing in the *spec/* folder), run
```
bundle exec rspec && yarn test
```

### Configure Heroku deployment
 * create Heroku app and link it to this repo

``` 
heroku buildpacks:add --index 1 heroku/nodejs
heroku buildpacks:add heroku/ruby
git push heroku
heroku rake db:migrate
heroku rake db:seed
```
It's currently deployed [here](https://rails-react-boilerplate.herokuapp.com).

## License

MIT © [Artem Vasiliev](https://github.com/artemv)
