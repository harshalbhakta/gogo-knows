##![Ruby on Rails](https://s3.amazonaws.com/gogo-knows/rails-banner.png)

### Kill Rails Server using PID
```ruby

$ ps aux | grep rails
$ kill -9 <pid>

```

### Create a rails app using a specific version of rails
```ruby

$ rails _3.2.11_ new AngularRaffler

```

### Check what is available on current RVM and update if required.
```ruby

# Check what is known to RVM
$ rvm list known


# If you don't see a specific version in there, ex. ruby 2.0.0-p247
# Execute below command to update the list
$ rvm get stable

# You should now see the new version of ruby.

```

### Rake task to drop, create, migrate & seed db in development mode.
```ruby

# Place below code snippet in the file /lib/tasks/db.rake
namespace :db do
  desc "Drop, create, migrate then seed the database"
  task :rdb => :environment do
    Rails.env = 'development'
    Rake::Task['db:drop'].invoke
    Rake::Task['db:create'].invoke
    Rake::Task['db:migrate'].invoke 
    Rake::Task['db:seed'].invoke
  end
end

# Execute below command to run the task
$ rake db:rdb
```

### Generate rdoc documentation.
```ruby

# Generate the documentaion for app folder.
$ rdoc app --op doc/app --all
```

### Production commands
```ruby

# db:seed
$ rake db:seed RAILS_ENV="production"

# db:migrate
$ rake db:migrate RAILS_ENV="production"

# start server in production mode
$ rails server -e production

# start console in production mode
$ bundle exec rails c production

````

### Allow slug with a dot(.)
````ruby 

# Use below regular expression in routes.rb

resources :users, :only => [:index, :show, :edit, :update, :destroy], :id => /[\w.]+/

````

### Redirect user to root after sign-up
````ruby

# app/controllers/users/registrations_controller.rb
class Users::RegistrationsController < Devise::RegistrationsController
  protected
      def after_sign_up_path_for(resource)
        root_path
      end  
end

# routes.rb
devise_for :users, :controllers => { :registrations => "users/registrations" }

````

### Before installing gem 'pg'
````ruby

$ sudo apt-get install postgresql
$ sudo apt-get install libpq-dev

````

### Before installing gem 'rmagick'
````ruby

$ sudo apt-get install imagemagick
$ sudo apt-get install libmagickwand-dev

````

#### hstore migration fails
````ruby

# PG::Error: ERROR:  could not open extension control file 
# "/usr/share/postgresql/9.1/extension/hstore.control": No such file or directory

$ sudo apt-get install postgresql-contrib

````

#### Unicorn kill process
````ruby

# Helpful when code chagnes don't reflect after cap deploy.
# Old unicorn processes keep serving previous version.

$ ps aux | grep 'unicorn' | awk '{print $2}' | xargs sudo kill -9

````
