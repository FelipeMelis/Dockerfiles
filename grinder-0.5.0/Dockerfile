# Import perl 
FROM perl:latest

MAINTAINER Felipe Melis <felipe.melis@gmail.com>

# Install cpanm for installing other perl packages

RUN curl -L http://cpanmin.us | perl - App::cpanminus
RUN cpanm install Module::Build
RUN cpanm Bio::Perl
RUN cpanm inc::Module::Install
RUN cpanm Getopt::Euclid
RUN cpanm Math::Random::MT 

# Download Grinder 0.5.0 and install Grinder

RUN curl -L -o Grinder-0.5.4.tar.gz https://sourceforge.net/projects/biogrinder/files/latest/Grinder-0.5.4.tar.gz
RUN tar -xzvf Grinder-0.5.4.tar.gz 
WORKDIR Grinder-0.5.4
RUN perl Makefile.PL 
RUN make
RUN make install



