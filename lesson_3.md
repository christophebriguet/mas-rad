# Lesson #3 (2014-05-20)

Learning about RSpec, TravisCI, GitHub Pull-Request workflow.
Goal: http://todomvc-rails.herokuapp.com

## Git starting guide

- http://gitimmersion.com
- http://rogerdudler.github.io/git-guide
- http://gitref.org
- http://git-scm.com/book


## Setup RSpec

- Follow installation: https://github.com/rspec/rspec-rails#installation
- $ bundle install
- $ rails generate rspec:install

## 'add_todo_validation' spec

- $ rails generate rspec:model todo
- Add 'validates title presence' in `spec/models/todo_spec.rb`

``` ruby
# spec/models/todo_spec.rb
require 'spec_helper'

describe Todo do
  it 'validates title presence' do
    todo = Todo.new(title: '')
    expect(todo).not_to be_valid
  end
end
```

- Commit & Push

## Setup TravisCI

- https://travis-ci.com
- http://docs.travis-ci.com/user/getting-started/
- $ gem install travis
- $ travis init
- add `gem 'rake'` in Gemfile and run `bundle install`
- edit `.travis.yml`

``` ruby
# .travis.yml
language: ruby
rvm:
- 2.1.1
addons:
  postgresql: "9.3"
before_script:
  - psql -c 'create database travis_ci_test;' -U postgres
  - cp config/database.yml.travis config/database.yml
```

- $ travis enable
- Commit & Push
- $ travis open
- Travis should failed because of the spec.

## Update your fork

- https://help.github.com/articles/syncing-a-fork
- $ git remote add upstream https://github.com/thibaudgg/thibaudgg/mas-rad-rails-app.git
- $ git fetch upstream
- $ git checkout master
- $ git merge upstream/master

## 'add_todo_validation' feature

- $ gco -b 'add_todo_validation'
- $ bundle install # for rspec-rails gem
- $ bundle exec rspec # should fail
- Add todo.rb model validation
- $ git add .
- $ git commit -m 'Add Todo validation on title presence'
- $ git push origin add_todo_validation
- Submit a Pull Request to thibaudgg from you GitHub repository (add_todo_validation branch)
- Check if your Pull Request is valid on travis
