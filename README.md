# lnx

a wrapper start docker in your shell with your files *now*

![screencast](screencast.gif)

## setup

    ln -s $(pwd)/lnx /usr/local/bin
    docker tag ubuntu:18.04 lnx

## usage

files are mapped from the host

    $ cd myfolder
    myfolder $ pwd
    /Users/you/myfolder
    myfolder $ lnx
    root@lnx:~/myfolder# pwd
    /Users/you/myfolder
    root@lnx:~/myfolder# apt-get update && apt-get install -y htop
    root@lnx:~/myfolder# exit

resume session:

    myfolder $ lnx
    root@lnx:~/myfolder# htop

Snapshot your state:

    $ docker commit lnx lnx-with-htop

Restore snapshot:

    $ docker tag lnx-with-htop lnx
    $ lnx
    $ htop
