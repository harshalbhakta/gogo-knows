Rake task to drop, create, migrate & seed db.
----
```ruby
# Place below code snippet in the file /lib/tasks/db.rake
namespace :db do
  desc "Drop, create, migrate then seed the database"
  task :rdb => :environment do
    Rake::Task['db:drop'].invoke
    Rake::Task['db:create'].invoke
    Rake::Task['db:migrate'].invoke 
    Rake::Task['db:seed'].invoke
  end

  #desc "Drop, create, migrate the database with RAILS_ENV=test"
  #task :trdb => :environment do
  #  Rails.env = 'test'
  #  Rake::Task['db:drop'].invoke
  #  Rake::Task['db:create'].invoke
  #  Rake::Task['db:migrate'].invoke
  #end
end

# Execute below command to run the task
$ rake db:rdb
```
