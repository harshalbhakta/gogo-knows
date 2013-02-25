##![Git](https://s3.amazonaws.com/gogo-knows/git-banner.png)

### Config
```ruby

# Set global username & email
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com

# Set global editor
$ git config --global core.editor sublime

# Set global mergetool
$ git config --global merge.tool kdiff3

# Check config list
$ git config --list

# Check individual config
$ git config user.name

```

### Feature branch workflow
```ruby
    
# Checkout a new branch for the new feature
$ git checkout -b feature_1

# Make changes for the feature & commit changes
$ git commit -a -m 'make changes for [feature_1]'

# Checkout a branch to merge the feature branch into it
$ git checkout master

# Merge the feature branch
$ git merge feature_1

# Delete the feature branch
$ git branch -d feature_1

# EXTRA
# In case of switching the workstation push the feature branch to the remote repository.
# Use the -u option to setup upstream references required for git pull.
$ git push -u origin feature_1
```

### Commit a single file with multiple modified files in the working directory.
```ruby
    
# Check current status
$ git status

# Check what has changed for the single file.
$ git diff HEAD app/models/quiz_user.rb

# Commit the changes made to the single file.
$ git commit -m "Add :entries_for_quizzes to quiz_user" app/models/quiz_user.rb
```

#### Remove multiple deleted files.
````ruby

# Changes not staged for commit:
#   (use "git add/rm <file>..." to update what will be committed)
#   (use "git checkout -- <file>..." to discard changes in working directory)
#
#	deleted:    app/views/admins/offer_codes/_form.html.erb
#	deleted:    app/views/admins/offer_codes/edit.html.erb
#	deleted:    app/views/admins/offer_codes/new.html.erb
#	deleted:    app/views/admins/offer_codes/show.html.erb
#	deleted:    app/views/admins/offers/_form.html.erb

$ git add -u

-u, --update

Only match <filepattern> against already tracked files in the index rather than the working tree. That means that it will never stage new files, but that it will stage modified new contents of tracked files and that it will remove files from the index if the corresponding files in the working tree have been removed.
If no <filepattern> is given, default to "."; in other words, update all tracked files in the current directory and its subdirectories.

Note: This adds the modified tracked files to the staging area as well so run this command only if you had just removed the files and want to stage them immediately. 

````

#### Git pretty log output with refs & branches.
````ruby

$ git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative"

````

#### Git amend a single file.
````ruby

# Consider 2 files have changed. a.txt & readme.MD

$ git add readme.MD

$ git commit -m "2 Files changed in this commit"

# We forgot to "git add a.txt". We use amend to add it to the previous commit.
# --no-edit skips opening the editor.

$ git add a.txt

$ git commit --amend --no-edit

# Changes to both files will now be in the same commit "2 Files changed in this commit"

````

#### Git alias for a command
````ruby

# Creates alias for "git po" -> "git push origin master"
$ git config --global alias.po "push origin master"


````
