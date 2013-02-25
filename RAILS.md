##![Ruby on Rails](https://s3.amazonaws.com/gogo-knows/rails-banner.png)

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