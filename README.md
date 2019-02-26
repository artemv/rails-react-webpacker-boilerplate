# Rails 5 / React / Webpacker boilerplate

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

This app is tested using *RSpec* and *Enzyme*. To run all tests (residing in the *spec/* folder), run
```
bundle exec rspec
```

JS tests are using *Mocha* and *Enzyme*. To run JS tests, run
```
yarn test
```

### Configure Heroku deployment
 * create Heroku app and link it to this repo
 * `heroku buildpacks:add --index 1 heroku/nodejs`
 * `heroku buildpacks:add heroku/ruby`
 * `git push heroku`

## License

MIT © [Artem Vasiliev](https://github.com/artemv)
