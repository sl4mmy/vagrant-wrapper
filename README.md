vagrant-wrapper
---------------
Wrapper script for executing Vagrant.

Building and running Vagrant is, unfortunately, quite a shit-show.
Rather than use something generic and somewhat standard, such as Chef's (nee Opscode) Omnibus,
the Vagrant team decided to roll their own.  Originally, this relied upon
a Hashicorp repository named puppet-modules, but that has since been replaced
by vagrant-installers.  The new vagrant-installers ultimately uses a tiny wrapper
utility written in Go to setup some environment variables and exec vagrant, but
this is all functionally equivalent to the old vagrant shell script generated by
puppet-modules.

Instead of dealing with the additional dependency of the Go compiler and a new
compilation step, I've just taken a copy of the shell script and hand-edited it to
be as generic as possible.
