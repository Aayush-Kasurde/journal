apt-get 
=======

Quick Guide to `apt-get`


* apt-get update

  This retrieves the current list of packages from all servers in your `sources.list`.
  If you don't do this from time to time your local list of available packages may become out of date.
  Do this occasionally before doing a `dist-upgrade` or searching for a new package.
  The package lists are large: doing an update may result in several MB of data being retrieved from the Internet.

* apt-cache search program

  This will do a keyword search through the list of available packages, including package names and descriptions.
  You can put in several keywords, for example `apt-cache search text editor` to find a list of text editors.

* apt-cache show program

  Once you've found a package that looks interesting using `apt-cache search`,you can display more detailed information about it using `apt-cache show program`. 
  This will tell you things like the size of the package (important if you are installing it off the Internet) and 
  an extended description, as well as what other packages it depends on in order to work and the name of the developer who maintains the package.

* apt-get install program

  This will get the latest version of the specified package and install it, along with any other packages that it depends on in order to work.
  If the requested package is already installed, this will upgrade it to the latest available version.

* apt-get remove program

  If you've previously installed a program and decide you don't want it anymore, you can remove it using this command.
  Because some software packages can depend on others, removing one program may break other programs.
  Running `apt-get remove` therefore checks first to see if any other software needs the program to work, and uninstalls them as well.
  This is just one example of the way the Debian package management tools have been designed to try to keep your computer in a sane state, without broken or half-installed software.
  It's certainly possible to break a Debian system, but generally you have to try to do it.
  It's unlikely you could do it by mistake.

* apt-get upgrade

  Over time, most of the software packages on your computer will become out of date as new versions are released to add features or fix bugs.
  You could manually do `apt-get install foo` on each one, but that's not very convenient, so Apt provides a simple way to upgrade your entire system at once.
  Just type `apt-get upgrade` to have Apt check every single package on your system for a new version, then download and install it.
  This command will never install new packages, it will only upgrade packages that are already installed.

* apt-get dist-upgrade

  Sometimes you'll have a software package installed, and a new version will come out that has a lot of new features and therefore it now depends on some other program to run.
  For example, you may have a movie player installed that supports a lot of different movie formats. When new formats come out, modules for those formats may be added in separate packages, so the latest version of the movie player software now depends on a new package that you don't yet have installed on your system.
  If you just do `apt-get upgrade`, you'll get the latest movie player, but you won't get all the new format packages. The `apt-get dist-upgrade` command solves that problem for you: not only does it get the latest version of every package already installed just like `apt-get upgrade`,it also installs any new packages they need that may not be on your system yet.
  If you want to keep your system up to date with all the latest updates and security patches, running `apt-get update; apt-get dist-upgrade` from time to time is the best way to do it.

* apt-get clean

  When you ask Apt to install a software package, it downloads the package and stores it in a cache on your disk before it does the actual installation.
  If you then remove the package, but later change your mind again and re-install it, Apt doesn't need to fetch it off the Internet again because the package is sitting in the local cache.
  That's great for saving bandwidth, but after a while it can use up space on your disk so it's a good idea to periodically delete old packages from the cache.
  Running `apt-get clean` will totally flush the package cache, possibly freeing up some precious disk space.
  Running this command is quite safe, because the worst that can happen is Apt may need to download a package again if you remove it then re-install it.

* apt-get autoclean

  This is almost the same as `apt-get clean`, except it's just a little bit smarter: instead of cleaning out your entire package cache, it deletes only superseded packages.
  For example, your package cache may contain packages for the last 7 versions of a text editor that has been upgraded a number of times: running `apt-cache autoclean` will delete the oldest 6 versions from the cache, leaving only the latest one.
  That makes sense because you're not likely to re-install anything except the latest version anyway. 
  This is also a very safe command to run, so if you're a bit tight on disk space and don't want your package cache growing too much you could put it in a Cron job to do an automatic cleanup from time to time. 
  There's really no reason to keep the older packages lying around on disk anyway.
