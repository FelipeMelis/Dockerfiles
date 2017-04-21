# Import an official image of Ubuntu
FROM ubuntu:17.04

# Install software 
RUN apt-get update
RUN apt-get install -y git
RUN apt-get install -y python2.7
RUN apt-get install -y python-pip
RUN apt-get install -y libdatetime-perl libxml-simple-perl libdigest-md5-perl default-jre bioperl

# Set the working directory to /app
WORKDIR /app

# Install prokka
RUN git clone https://github.com/tseemann/prokka.git

# Install python packages
RUN pip install --upgrade pip
RUN pip install numpy matplotlib pandas sympy nose
RUN pip install biopython

