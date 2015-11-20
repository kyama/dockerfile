From ubuntu:15.10

RUN apt-get update && apt-get -y install build-essential 
RUN apt-get update && apt-get -y install gcc g++ make autoconf automake libtool libpng-dev libjpeg-dev libgif-dev libssl-dev libyaml-dev libsqlite3-dev libleveldb-dev libmysqlclient-dev

#RUN bash -c 'debconf-set-selections <<< "mysql-server mysql-server/root_password password root"'
#RUN bash -c 'debconf-set-selections <<< "mysql-server mysql-server/root_password_again password root"'

RUN apt-get update && apt-get -y install ruby ruby-dev

RUN apt-get update && apt-get -y install curl tar
RUN curl -OJL https://github.com/nagadomi/eiio/archive/v0.5.6.tar.gz && \
    tar -xzvf eiio-0.5.6.tar.gz && \
    cd eiio-0.5.6 && \
    ./autogen.sh && \
    ./configure --with-arch=corei7 && \
    make && \
    make install && \
    ldconfig

RUN curl -OJL https://github.com/nagadomi/nv/archive/v2.2.0.tar.gz && \
    tar -xzvf nv-2.2.0.tar.gz && \
    cd nv-2.2.0 && \
    ./autogen.sh && \
    ./configure --with-arch=corei7 && \
    make && \
    make install && \
    ldconfig
RUN curl -OJL https://github.com/nagadomi/otama/archive/v0.7.3.tar.gz && \
    tar -xzvf otama-0.7.3.tar.gz && \
    cd otama-0.7.3 && \
    ./autogen.sh && \
    ./configure --enable-mysql && \
    make && \
    make check && \
    make install && \
    ldconfig

RUN gem install bundle
