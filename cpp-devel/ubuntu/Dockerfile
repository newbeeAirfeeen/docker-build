FROM gcc:11.2.0

RUN apt-get update -y && apt-get upgrade -y && apt-get install -y libmpc-dev \
                      libgmp-dev libmpfr-dev libssl-dev

COPY ../gdb-11.2.tar.gz ./
RUN tar -zxvf gdb-11.2.tar.gz && cd gdb-11.2 && ./configure \
                    && make -j 4 \
                    && make install

COPY ../cmake-v3.23.0-rc5.tar.gz ./ 
RUN tar -zxvf cmake-v3.23.0-rc5.tar.gz && cd cmake-v3.23.0-rc5 \
                    && ./bootstrap \
                    && make -j 4 \
                    && make install  
