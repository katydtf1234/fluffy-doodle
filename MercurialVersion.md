# Mercurial

The source repository for this project has external references to Subversion sub-repositories. This has been supported by Mercurial since [version 1.5](http://mercurial.selenic.com/wiki/Subrepository#SVN_subrepositories).

If you still have an older version of Mercurial or if you don't have Subversion installed on your computer, you won't be able to check out the source tree.

You can check if everything is set up correctly by typing ` hg --version ` and ` svn --version `.

# Ubuntu

Some popular versions of Ubuntu still ship with older versions of Mercurial. Here is how you fix that.

  1. Type ` sudo apt-get update; sudo apt-get install mercurial subversion `.
> > Among other things, this makes sure you have all the required
> > dependencies.

  1. Go to the [Ubuntu FTP server](ftp://ftp.ubuntu.com/ubuntu/pool/universe/m/mercurial/) and download a recent copy of Mercurial. Something like [mercurial-common\_1.7.5-1ubuntu1\_all.deb](ftp://ftp.ubuntu.com/ubuntu/pool/universe/m/mercurial/mercurial-common_1.7.5-1ubuntu1_all.deb), and [mercurial\_1.7.5-1ubuntu1\_amd64.deb](ftp://ftp.ubuntu.com/ubuntu/pool/universe/m/mercurial/mercurial_1.7.5-1ubuntu1_amd64.deb) or [mercurial\_1.7.5-1ubuntu1\_i386.deb](ftp://ftp.ubuntu.com/ubuntu/pool/universe/m/mercurial/mercurial_1.7.5-1ubuntu1_i386.deb) should work for most users.

  1. Install the downloaded packages with ` sudo dpkg -i mercurial*deb `.

  1. Type ` hg --version ` to verify that you are now at version ` 1.7.5 `.

  1. You should now be able to check out the source repository.