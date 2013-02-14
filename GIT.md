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
