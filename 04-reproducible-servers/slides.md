!SLIDE
# Server Provisioning

!SLIDE bullets incremental
* How long does it take to create a server by hand?
* How sure are you the second one acts the same?

!SLIDE
    @@@ Sh
    #!/bin/bash -ex
    
    source ../../shared/setup.sh
    
    cd /tmp/build
    
    PACKAGE=httpd
    VERSION=2.2.22
    DESTDIR=/tmp/fpm/$PACKAGE-$VERSION
    mkdir -p $DESTDIR
    export DESTDIR
    
    wget --no-verbose "http://archive.apache.org/dist/httpd/httpd-$VERSION.tar.gz"
    tar -zxf httpd-$VERSION.tar.gz
    cd httpd-$VERSION
    # We need to use the included version of apr:
    # http://apache-http-server.18135.n6.nabble.com/Bug-53162-New-Cannot-compile-Apache-2-2-22-td4940024.html
    ./configure --prefix=/etc/httpd \
                --bindir=/usr/bin \

!SLIDE bullets
* Puppet
* Chef
* Ansible
* Salt

