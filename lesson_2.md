# Lesson #2 (2014-05-13)


## Finish RailsForZombies

- http://railsforzombies.org (to complete level 4/5 & 5/5)

## Goal: http://todomvc-rails.herokuapp.com

### Rails new

- Create new Rails box on https://www.nitrous.io
- Install postgresql: http://help.nitrous.io/postgresql/
- $ parts install postgresql
- $ parts start postgresql
- $ ruby --version
- http://guides.rubyonrails.org/getting_started.html
- $ rails --version
- Check on https://rubygems.org/gems/rails the last gem version
- $ gem update rails
- $ rails -v
- $ rails --help
- $ rails new todo_app --database=postgresql --skip-test-unit --skip-spring
- Overview of rails folders/files
- config.ru: http://rack.github.io, ruby webserver interface
- Gemfile: http://bundler.io, gem dependencies management

### Launch server

- $ cd todo_app
- $ rails -h
- $ rails server
- Doh! server error
- $ rake db:create
- $ rails s (shorcut of 'server')
- See root page

### Generate simple todo scaffold

- http://guides.rubyonrails.org/generators.html
- $ rails generate -h
- $ rails generate scaffold todo title completed:boolean
- $ rails s
- Doh! server error
- $ rake db:migrate
- $ rails server

### Change root path (/)

- $ rake --tasks
- $ rake routes
- add `root 'todos#index'` to config/routes.rb

### Fork from Github and Setup Nitrous.io

- Add you public ssh key to github: http://help.nitrous.io/github-add-key
- $ parts install postgresql
- $ parts start postgresql
- $ git clone git@github.com:<your github name>/mas-rad-rails-app.git todo_app
- $ git config --global user.email <your email>
- $ git config --global user.name '<your name>'
- $ cd todo_app
- $ bundle install
- $ rake db:create db:migrate
- $ rails s

# Exercices

- Create a https://codeclimate.com account and complete http://railsforzombies.org (level 4/5 & 5/5)

# Media

- http://railsforzombies.org videos and [slides](http://railsforzombies.com.s3.amazonaws.com/Rails-For-Zombies-Slides.pdf).
