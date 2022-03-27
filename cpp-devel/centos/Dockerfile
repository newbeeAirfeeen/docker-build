FROM gcc:11.2.0

RUN yum update -y && yum upgrade -y && yum install -y mpc-dev \
                      gmp-devel mpfr-devel openssl-dev

COPY ../gdb-11.2.tar.gz ./
RUN tar -zxvf gdb-11.2.tar.gz && cd gdb-11.2 && ./configure \
                    && make -j 4 \
                    && make install

COPY ../cmake-v3.23.0-rc5.tar.gz ./ 
RUN tar -zxvf cmake-v3.23.0-rc5.tar.gz && cd cmake-v3.23.0-rc5 \
                    && ./bootstrap \
                    && make -j 4 \
                    && make install  
