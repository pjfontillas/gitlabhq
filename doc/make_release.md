# Things to do when creating new release
NOTE: This is a guide for GitLab developers. If you are trying to install GitLab see the latest stable [installation guide](install/installation.md) and if you are trying to upgrade, see the [upgrade guides](update).

## Install guide up to date?

* References correct GitLab branch `x-x-stable` and correct GitLab shell tag?

## Make upgrade guide

### From x.x to x.x

#### 0. Any major changes? Database updates? Web server change? File structure changes?

#### 1. Make backup

#### 2. Stop server

#### 3. Do users need to update dependencies like `git`?

#### 4. Get latest code

#### 5. Does GitLab shell need to be updated?

#### 6. Install libs, migrations, etc.

#### 7. Any config files updated since last release?

Check if any of these changed since last release (~22nd of last month depending on when last release branch was created):

* https://github.com/gitlabhq/gitlabhq/commits/master/lib/support/nginx/gitlab
* https://github.com/gitlabhq/gitlab-shell/commits/master/config.yml.example
* https://github.com/gitlabhq/gitlabhq/commits/master/config/gitlab.yml.example
* https://github.com/gitlabhq/gitlabhq/commits/master/config/unicorn.rb.example
* https://github.com/gitlabhq/gitlabhq/commits/master/config/database.yml.mysql
* https://github.com/gitlabhq/gitlabhq/commits/master/config/database.yml.postgresql

#### 8. Need to update init script?

Check if changed since last release (~22nd of last month depending on when last release branch was created): https://github.com/gitlabhq/gitlabhq/commits/master/lib/support/init.d/gitlab

#### 9. Start application

#### 10. Check application status

## Make sure the code quality indicatiors are good

* [![build status](http://ci.gitlab.org/projects/1/status.png?ref=master)](http://ci.gitlab.org/projects/1?ref=master) on ci.gitlab.org (master branch)

* [![build status](https://secure.travis-ci.org/gitlabhq/gitlabhq.png)](https://travis-ci.org/gitlabhq/gitlabhq) on travis-ci.org (master branch)

* [![Code Climate](https://codeclimate.com/github/gitlabhq/gitlabhq.png)](https://codeclimate.com/github/gitlabhq/gitlabhq)

* [![Dependency Status](https://gemnasium.com/gitlabhq/gitlabhq.png)](https://gemnasium.com/gitlabhq/gitlabhq) this button can be yellow (small updates are available) but must not be red (a security fix or an important update is available)

* [![Coverage Status](https://coveralls.io/repos/gitlabhq/gitlabhq/badge.png?branch=master)](https://coveralls.io/r/gitlabhq/gitlabhq)

## Make a release branch

After making the release branch new commits are cherry-picked from master. When the release gets closer we get more selective what is cherry-picked.

- 5 days before release: feature freeze
- 3 days before release: UI freeze
- 1 day before release: code freeze

## Last actions

1. Write a blog post (mention what GitLab is on the first line, select a MVP)
1. Update VERSION and CHANGELOG
1. Create a git tag vX.X.X
1. Publish the blog post
1. Tweet about the release
