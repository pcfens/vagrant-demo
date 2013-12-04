# vagrant-bare

A bare vagrant machine set up to be provisioned with puppet.

## Use

Edit puppet/manifests/site.pp to describe the system state that you want after running `vagrant up`.

Modules are expected to be kept in puppet/modules, which is customarily managed by [librarian-puppet](https://github.com/rodjek/librarian-puppet).

### librarian-puppet

Edit the file `puppet/Puppetfile` to list modules that you need available to your manifest file.
The modules can be pulled from the puppet forge, or from git repositories.

Run `librarian-puppet install` while in the puppet/ directory to fetch the modules and their 
dependencies.

### Custom/local modules

librarian-puppet won't interfere with any modules that you manually add to the modules directory,
but will overwrite any changes you've made to managed modules.  librarian-puppet only does things
when manually called.
