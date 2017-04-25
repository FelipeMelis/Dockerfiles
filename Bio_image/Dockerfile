# Import an official image of centOS
FROM centos:7

MAINTAINER Felipe Melis <felipe.melis@gmail.com>

# Install software
RUN yum -y update
RUN yum install -y wget

# Download BCL2FASTQ
RUN wget ftp://webdata:webdata@ussd-ftp.illumina.com/Downloads/Software/bcl2fastq/bcl2fastq-1.8.4-Linux-x86_64.rpm

# 

# 
# FROM ubuntu:17.04
#
# 
#
# # Install software
# RUN apt-get update
# RUN apt-get install -y wget
# RUN apt-get install -y imagemagick
# RUN apt-get install -y git
# RUN apt-get install -y python2.7
# RUN apt-get install -y python-pip
# RUN apt-get install -y libdatetime-perl libxml-simple-perl libdigest-md5-perl default-jre bioperl
#
# # Set the working directory to /app
# WORKDIR /app
#
# # Install prokka
# RUN git clone https://github.com/tseemann/prokka.git
#
# #
# RUN wget ftp://webdata:webdata@ussd-ftp.illumina.com/Downloads/Software/bcl2fastq/bcl2fastq-1.8.4-Linux-x86_64.rpm
#
# # Install python packages
# RUN pip install --upgrade pip
# RUN pip install numpy matplotlib pandas sympy nose
# RUN pip install biopython
#
# # Install BCL2FASTQ
# RUN apt-get install -y rpm
# RUN apt-get install -y imagemagick
# RUN rpm -i bcl2fastq-1.8.4-Linux-x86_64.rpm
#
