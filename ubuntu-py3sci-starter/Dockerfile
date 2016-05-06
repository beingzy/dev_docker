# 14.04 ubuntu trusty
FROM ubuntu:14.04

MAINTAINER Yi Zhang <beingzy@gmail.com>

LABEL "os"="ubuntu:14.04" "purpose"="Python,R"

# add 
RUN sudo sh -c 'echo "deb http://cran.rstudio.com/bin/linux/ubuntu trusty/" >> /etc/apt/sources.list'

RUN sudo apt-get -y update --fix-missing
    
RUN apt-get install -y \
    python3-pip \
    python-dev \
    libev4 \
    libev-dev \
    gcc \
    libxslt-dev \
    libxml2-dev \
    libffi-dev

RUN sudo apt-get install -y \ 
    build-essential \
	gfortran

RUN sudo apt-get install -y \
    liblapack-dev \
    liblapack-doc-man \
    liblapack-doc \
    liblapack-pic \
    liblapack3 \
    liblapack-test \
    liblapack3gf \
    liblapacke \
    liblapacke-dev
    
RUN sudo apt-get -y install r-base \
                            r-base-dev 

# add project
ADD . /

# install dependency
RUN pip3 install scipy \
                 numpy \
                 scikit-learn \
                 rpy2