# Import an official image of Ubuntu
FROM ubuntu:17.04

# Updating and installing essential stuff
RUN apt-get update
RUN apt-get -y install wget
RUN apt-get -y install python2.7
RUN apt-get -y install python-pip 
RUN apt-get install -y unzip
RUN apt-get install -y python3-setuptools
RUN easy_install3 pip
RUN pip install configparser

# Adding Biolinux repos
RUN echo "deb http://nebc.nerc.ac.uk/bio-linux/ unstable bio-linux" >> /etc/apt/sources.list
RUN echo "deb http://ppa.launchpad.net/nebc/bio-linux/ubuntu trusty main" >> /etc/apt/sources.list
RUN echo "deb-src http://ppa.launchpad.net/nebc/bio-linux/ubuntu trusty main" >> /etc/apt/sources.list
RUN apt-get update
RUN apt-get install -y --allow-unauthenticated bio-linux-keyring

# Installing Bioformat
RUN apt-get install -y biom-format-tools

# Installing Fastx toolkit
RUN apt-get install -y fastx-toolkit

# Installing pipits-1.4.2
WORKDIR /root
RUN wget https://github.com/hsgweon/pipits/archive/1.4.2.tar.gz
RUN tar -xzvf 1.4.2.tar.gz
WORKDIR /root/pipits-1.4.2
RUN python setup.py clean --all
RUN python setup.py install --prefix=/root/pipits

# Setting the dir for installing de pipits stuff
WORKDIR /root/pipits

# Installing ITSx
RUN wget http://microbiology.se/sw/ITSx_1.0.11.tar.gz
RUN tar -xzvf ITSx_1.0.11.tar.gz
RUN ln -s /root/pipits/ITSx_1.0.11/ITSx bin/ITSx
RUN ln -s /root/pipits/ITSx_1.0.11/ITSx_db bin/ITSx_db

# Installing VSEARCH
RUN wget https://github.com/torognes/vsearch/releases/download/v2.1.2/vsearch-2.1.2-linux-x86_64.tar.gz
RUN tar -xvzf vsearch-2.1.2-linux-x86_64.tar.gz
RUN ln -s /root/pipits/vsearch-2.1.2-linux-x86_64/bin/vsearch bin/vsearch

# Installing PEAR
RUN wget http://sco.h-its.org/exelixis/web/software/pear/files/pear-0.9.10-bin-64.tar.gz
RUN tar xvfz pear-0.9.10-bin-64.tar.gz
RUN ln -s /root/pipits/pear-0.9.10-bin-64/pear-0.9.10-bin-64 bin/pear

# Installing RDP Classifier 
RUN wget https://sourceforge.net/projects/rdp-classifier/files/rdp-classifier/rdp_classifier_2.12.zip
RUN unzip rdp_classifier_2.12.zip
RUN ln -s rdp_classifier_2.12/dist/classifier.jar ./classifier.jar

# Installing Hmmer 
RUN apt-get install -y hmmer

# Installing Java runtime
RUN apt-get install -y default-jre

# Download the reference databases
RUN mkdir -p /root/pipits/refdb
WORKDIR /root/pipits/refdb
RUN wget http://sourceforge.net/projects/pipits/files/UNITE_retrained_22.08.2016.tar.gz
RUN tar -xzvf UNITE_retrained_22.08.2016.tar.gz
RUN wget https://unite.ut.ee/sh_files/uchime_reference_dataset_01.01.2016.zip
RUN unzip uchime_reference_dataset_01.01.2016.zip

# Set PATH and Environment Variable

WORKDIR /root
RUN echo "export PATH=/root/pipits/bin:$PATH" >> .bashrc
RUN echo "export PYTHONPATH=/root/pipits/lib/python2.7/site-packages:$PYTHONPATH" >> .bashrc
RUN echo "export PIPITS_UNITE_REFERENCE_DATA_CHIMERA=/root/pipits/refdb/uchime_reference_dataset_01.01.2016/uchime_reference_dataset_01.01.2016.fasta" >> .bashrc
RUN echo "export PIPITS_UNITE_RETRAINED_DIR=/root/pipits/refdb/UNITE_retrained" >> .bashrc
RUN echo "export PIPITS_WARCUP_RETRAINED_DIR=/root/pipits/refdb/warcup_retrained_V2" >> .bashrc
RUN echo "export PIPITS_RDP_CLASSIFIER_JAR=/root/pipits/classifier.jar" >> .bashrc

# Solving some problems
RUN pip2 install configparser 
RUN apt-get install -y python-numpy
# RUN export LC_ALL=C.UTF-8
# RUN export LANG=C.UTF-8
