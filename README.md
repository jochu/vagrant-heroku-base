vagrant-heroku-base
==================

Minimal [vagrant base box][basebox] for matching Heroku Celadon Cedar stack.

It matches hardware's memory limitations and provides only the minimal software requirements 
for vagrant. This box uses versions of ruby (1.9.2p290) and rubygems (1.3.7) that, at time of 
writing, match those on Heroku.

Usage
-----

In your Vagrantfile add the following:

```ruby
  config.vm.box = "heroku-base"
  config.vm.box_url = "https://github.com/downloads/jochu/vagrant-heroku-base/heroku-base.box"
```

It is recommended you [package your own box][packaging] after you've install the necessary
dependencies for your application.

Motivation
----------

This box was based off of [ejholmes' vagrant-heroku][vagrant-heroku] and 
[vagrant's lucid64.box][lucid64]'s postinstall.sh - however, unlike vagrant-heroku, this box
only only includes the minimum needed for vagrant. The rest of heroku stack is left for user 
to build on top this box.

This was made because it's a smaller payload and it's easier to add new things to a minimal box than
it is to change/upgrade a full-fledged box. This makes it easier to match moving targets like
Heroku's postgresql version.

  [basebox]: http://vagrantup.com/v1/docs/base_boxes.html
  [packaging]: http://vagrantup.com/v1/docs/getting-started/packaging.html
  [lucid64]: http://files.vagrantup.com/lucid64.box
  [vagrant-heroku]: https://github.com/ejholmes/vagrant-heroku