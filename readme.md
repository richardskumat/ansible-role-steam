ansible-role-steam
=========

Installs steam on Debian.

Currently only works on Debian 9, however it shouldn't be hard to Ubuntu 16.04 or 18.04 as they have similar
package names.

I believe Ubuntu's steam package has no prompt to accept steam's licensing, they've automated
it away.

Requirements
------------

Graphical X11 environment on a linux device.

Role Variables
--------------

```
# stretch backports have the 4.19 lts kernel
kernel_version: "4.19.0-0.bpo.5-amd64"
```

This is the var for the backports kernel version, can be found with:

```
apt-cache search linux-image-4.19 amd64 | grep -v 'cloud\|rt\|headers'
```

Since buster has been released in 2019/07, it's unlikely Stretch will have a newer backported kernel.

```
apt_src_main_url: 'http://cdn-fastly.deb.debian.org/debian'
apt_src_security_url: 'http://security.debian.org/'
raspbian_debian_mirrors: 'http://raspbian.raspberrypi.org/raspbian/'
raspbian_specific_mirrors: 'http://archive.raspberrypi.org/debian/'
```

Raspbian vars are unused, however the other vars are used in templating.

Dependencies
------------

None.

License
-------

GPLv3

Author Information
------------------

Richard Skumat

Link:

https://github.com/richardskumat
