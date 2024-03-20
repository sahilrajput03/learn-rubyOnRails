# README - Abandoned temporarily..

A command like `gem install jekyll bundler` installs both `Jekyll` and `Bundler` gems globally on your system. When you use `gem install`, it installs the specified gem(s) into the system's global gem repository, making them available system-wide for all users and projects.

Ensure that you have the latest versions of Bundler and RubyGems installed on your system by running:
`sudo gem update --system`. 


```bash
# Create a new app
rails new demo
cd demo
rails generate scaffold post title:string content:text
```

## Learning sources:

- Simple Ruby on Rails 5 REST API From Scratch ~ Traversy Media: https://www.youtube.com/watch?v=QojnRc7SS9o
- Ruby On Rails In 60 Minutes ~ Traversy Media:  https://www.youtube.com/watch?v=pPy0GQJLZUM

# Installing `rails` and creating a backend API project

```bash
# Install Rails using gem (Ruby's package manager)
gem install rails

# Create a new Rails project
rails new my_api --api
```
