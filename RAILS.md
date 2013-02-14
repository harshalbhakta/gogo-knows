Rake task to drop, create, migrate & seed db in development mode.
----
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
