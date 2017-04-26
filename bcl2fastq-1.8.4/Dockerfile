# Import an official image of centOS
FROM centos:7

MAINTAINER Felipe Melis <felipe.melis@gmail.com>

# Install software
RUN yum -y update
RUN yum install -y wget

# Install dependencies for BCL2FASTQ
RUN yum install -y ImageMagick
RUN yum install -y gnuplot
RUN yum install -y libxslt
RUN yum install -y kernel-devel
RUN yum install -y perl-XML-Simple

# Set the working directory to /app
RUN mkdir app
WORKDIR /app

# Download and install BCL2FASTQ
RUN wget ftp://webdata:webdata@ussd-ftp.illumina.com/Downloads/Software/bcl2fastq/bcl2fastq-1.8.4-Linux-x86_64.rpm
RUN rpm -i bcl2fastq-1.8.4-Linux-x86_64.rpm 