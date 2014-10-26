Snort boxes
===========
This repo provides Vagrantfile(s) to quickly install Snort on a clean system.
If you don't know what vagrant is then you are doing it wrong [Visit VagrantUP](https://www.vagrantup.com/).


Deployment
==========

After installing Vagrant (and maybe virtualbox), you can install
a fresh snort environment as so:

```bash
git clone https://github.com/wtfbbqhax/Snort-boxes.git snort-boxes
cd snort-boxes/
vagrant up
vagrant ssh
```

Missing Environments
====================

I currently only have Ubuntu 14.04 x86_64 as an environment. Snort has
official support on many more however. The following environments 
need to be created.

* Ubuntu    (86)
* Fedora    (86/64)
* Debian    (86/64)
* OpenSUSE  (86/64)
* FreeBSD   (86/64)
* OpenBSD   (32/64)
* TBD!!! (This list needs to be fleshed out)

Missing Packages
================

Many Snort users use many additional tools. It would be fantastic if
Someone could add some of these additional packages into the vagrantfile(s).

* Barnyard2
* Pulledpork
* Snorby / BASE / ACID (maybe) / etc

Also Missing
============

Are you a VIM user? Checkout my new syntax highlighter for "snort.conf".
_note to self: I need to submit this to VIM upstream to replace hog.vim_

https://github.com/wtfbbqhax/Snort-vim

I recommend using pathogen for managing vim plugins.




