FROM ubuntu

RUN apt-get update
RUN apt-get install -y build-essential python git wget

#clone MITK.git
RUN git clone https://github.com/kaiser-team/MITK.git
RUN mkdir MITK-build
RUN cd MITK-build

#install latest cmake
RUN apt-get install -y make
RUN wget -O cmake.sh https://github.com/Kitware/CMake/releases/download/v3.15.5/cmake-3.15.5-Linux-x86_64.sh && sh ./cmake.sh --prefix=/usr/local --skip-license


#install qt5
RUN apt-get install -y libfontconfig1
RUN apt-get install -y mesa-common-dev

RUN apt-get install -y qtbase5-dev
RUN apt-get install -y qtdeclarative5-dev

RUN cmake ../MITK
RUN make -j4
