# Ruby on Rails

A framework that make building web applications easier.
Gives a lot of features and helpers to make building web apps faster.

## Config Timezone

config/application.rb

```ruby
config.time_zone = 'Eastern Time (US & Canada)'
```

## switch database from sqlite3 to postgresql

1. Change gemfile from gem 'sqlite3' to

```
gem 'pg'
```

run `bundle`

2. Update database.yml in config folder

Update the adapter on the default to postgresql. use name of app and environment for database names.

> not a full file just a snippet of important lines

```
default: &default
  adapter: postgresql

development:
  <<: *default
  database: todo_34_development

test:
  <<: *default
  database: todo_34_test

production:
  <<: *default
  database: todo_34_production
```

3. make sure seeds file is up to date.
4. `rails db:drop`
5. `rails db:create`
6. `rails db:migrate`
7. `rails db:seed`

## Setting up a Project

1. `rails new todo_app --database=sqlite3 --skip-coffee -T`
   Creates a new app called todo_app with the database sqlite3, skips coffeescript setup and skips tests since we will be setting up rspec and not the default minitest
2. `cd todo_app`

3. `rails server` or `rails s`

```

git add .
git commit -m "initial commit"

```

4. `rm .ruby-version` remove locking in to a specific ruby version instead add to Gemfile `ruby "~> 2.6"`. Means about 2.6 basically 2.6 our higher.

```

git add .
git commit -m "more inclusive Ruby versioning"

```

5. `touch CODEOWNERS` a github file that will state a person or team that is responsible for merging in code.

https://help.github.com/articles/about-codeowners/

CODEOWNERS

```

# Be nice to these people:

# https://github.com/orgs/wyncode/teams/codeowners/members

# Only they can approve your pull requests!

- @wyncode/CodeOwners

```

```

git add .
git commit -m "set up CODEOWNERS"

```

6. Create a `Readme.md` file.

```

git commit README.md -m "update README"

```

7. Create GitHub repository. Grab URL and setup local git to have a remote for github.

GitHub repo will be called origin.

```

git remote add origin git@github.com:wyncode/todo.git
git push -u origin master

```

## Collaboration - Working with other people

- Read the routes file
- run the tests

If you run into migration pending after a pull request gets merged the easiest solution is to recreate your development database.

`rails db:drop db:create db:migrate db:seed`

## Semantic Versioning

Given a version number MAJOR.MINOR.PATCH, increment the:

- MAJOR version when you make incompatible API changes,

- MINOR version when you add functionality in a backwards-compatible manner, and

- PATCH version when you make backwards-compatible bug fixes.

> Additional labels for pre-release and build metadata are available as extensions to the MAJOR.MINOR.PATCH format.

## Actions / HTTP Methods

New - form to create
Create - Post request to create

Edit - form to update
Update - path/put request to update

Index - show all records
Show - show individual records

Destroy - delete a single record

## CSS

How to scope to individual pages?

## ERB

<% %> = ruby code
<%= %> = ruby code but output will be put on the screen

## Generator

`rails g scaffold` - creates a model, controller, migration, ...
`rails g model` - creates a new model
`rails g migration` - create a new migration

```bash
rails g migration AddCoursesToStudents course:belongs_to
```

## Scopes

A way to name a specific active record relation. Scopes should return an active record relation so that you can chain them.

```
scope :completed, -> { where(completed: true) }
```

> The `->` are called lamdas they are like an annomous fuction. scope will create a new method that will return something.

## Testing

RSPEC - a testing library for ruby  
`rspec-rails` - a testing gem with rails helpers built into it.

> `Regressions` - make sure new code doesn't break existing functionality.

model tests - (unit tests) at least all public methods on models  
system tests - (integration tests) fire up a browser and test them [capybara, selinium, chrome-driver, cypress]

`capybara` - uses selinium to open a chrome browser and navigate and click around

https://devhints.io/capybara
