# 14.04 ubuntu trusty
#
#
# this built docker images is available at
# beingzy/ds-env-py3-r
FROM ubuntu:14.04

MAINTAINER Yi Zhang <beingzy@gmail.com>

LABEL "os"="ubuntu:14.04" "purpose"="Python,R"

# prepare the environment for R installation
RUN sudo sh -c 'echo "deb http://cran.rstudio.com/bin/linux/ubuntu trusty/" >> /etc/apt/sources.list'
RUN gpg --keyserver keyserver.ubuntu.com --recv-key E084DAB9
RUN gpg -a --export E084DAB9 | sudo apt-key add -

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

RUN sudo apt-get install -y liblapack-dev \
                            liblapack-doc-man \
                            liblapack-doc \
                            liblapack-pic \
                            liblapack3 \
                            liblapack-test \
                            liblapack3gf \
                            liblapacke \
                            liblapacke-dev

RUN sudo apt-get install -y r-base \
                            r-base-dev \
                            libcurl4-gnutls-dev \
                            libxml2-dev \
                            libssl-dev

# install scientific computing libraries
RUN sudo apt-get install -y python3-scipy \
                            python3-numpy \
                            python3-pandas \
                            python3-sqlalchemy
                            
RUN sudo pip3 install scikit-learn \
                      rpy2 \
                      networkx \
                      nltk \
                      tqdm \
                      awscli \
                      boto3 \
                      alchemy
                      
RUN sudo pip3 install -U pandas
# python web stack
RUN sudo pip3 install flask \
                      flask-api \
                      flask-restful \
                      django

# install some R packages
RUN sudo su - -c "R -e \"install.packages(c('shiny', 'devtools'), repos = 'http://cran.rstudio.com/')\""
