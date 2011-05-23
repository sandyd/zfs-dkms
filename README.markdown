Native ZFS for Linux! ZFS is an advanced file system and volume manager
which was originally developed for Solaris. It has been successfully 
ported to FreeBSD and now there is a functional Linux ZFS kernel port
too. The port currently includes a fully functional and stable SPA, DMU,
and ZVOL with a ZFS Posix Layer (ZPL) on the way!

This is an experimental DKMS module configuration
To use,
    
    $ git clone git://github.com/sandyd/spl-dkms.git
    $ cd spl-dkms
    $ ./configure --prefix=/usr
    $ make
    $ sudo make install
    $ cd ../
    $ git clone git://github.com/sandyd/zfs-dkms.git
    $ cd zfs-dkms
    $ ./configure --prefix=/usr
    $ make
    $ sudo make install
    $ cd ../
    $ sudo mv zfs-dkms /usr/src/zfs-1.0
    $ sudo mv spl-dkms /usr/src/spl-1.0
    $ sudo rm -rf /lib/modules/`uname -r`/addon/zfs
    $ sudo rm -rf /lib/modules/`uname -r`/addon/spl
    $ sudo dkms add -m spl -v 1.0
    $ sudo dkms add -m zfs -v 1.0
    $ sudo dkms build -m spl -v 1.0
    $ sudo dkms build -m zfs -v 1.0
    $ sudo dkms install -m spl -v 1.0
    $ sudo dkms install -m zfs -v 1.0
