FROM ghcr.io/acdh-oeaw/generic-environments/shell:latest 
## Docker with ALL my perl Modules installed 

MAINTAINER Hannes Pirker <hannes.pirker@oeaw.ac.at>

RUN apt-get -y update && \
apt-get install -y libxml2-dev && \
apt-get install -y libxslt-dev && \
apt-get install -y libgdbm-dev && \
apt-get install -y zlib1g-dev && \
apt-get install -y libexpat1-dev && \
apt-get install -y perl-doc && \
apt-get install -y libstring-diff-perl && \
cpanm Archive::SevenZip && \
cpanm Archive::Tar && \
cpanm Archive::Zip && \
cpanm CHI::Memoize && \
cpanm Cpanel::JSON::XS  && \
cpanm Compress::Raw::Lzma && \
cpanm Data::Dumper && \
cpanm Data::Dumper::Simple && \
cpanm Date::Calc   && \
cpanm Date::Time && \
cpanm Digest::MD5 && \
cpanm Encoding::FixLatin && \
cpanm Excel::Writer::XLSX   && \
cpanm Expect && \
cpanm File::Basename && \
cpanm File::Copy && \
cpanm File::Find::utf8 && \
cpanm File::Path && \
cpanm File::Slurp && \
cpanm File::Slurper && \
cpanm File::Spec && \
cpanm HTML::Entities  && \
cpanm HTML::Escape   && \
cpanm IO::Compress::Base && \
cpanm IO::Compress::Bzip2 && \
cpanm IO::Uncompress::Bunzip2 && \
cpanm IO::Compress::Xz && \
cpanm IO::Uncompress::UnXz && \
cpanm IO::Stty && \
cpanm IO::Zlib && \
cpanm IPC::System::Simple && \
cpanm LWP::UserAgent && \
cpanm Math::Roman && \
cpanm Moose  && \
cpanm MooseX && \
cpanm MooseX::ClassAttribute && \
cpanm RDF::Query && \
cpanm RDF::Simple && \
cpanm RDF::Trine && \
cpanm RDF::Trine::Store::DBI::SQLite && \
cpanm Readonly && \
cpanm Scalar::Util && \
cpanm Set::Scalar && \
cpanm Spreadsheet::ParseExcel   && \
cpanm Spreadsheet::ParseXLSX   && \
cpanm Spreadsheet::Read   && \
cpanm Spreadsheet::ReadSXC   && \
cpanm Spreadsheet::WriteExcel   && \
cpanm Switch  && \
cpanm Text::CSV && \
cpanm Text::CSV::Hashify  && \
cpanm Text::CSV::Slurp && \
cpanm Text::CSV_XS && \
cpanm Text::Unidecode && \
cpanm Tie::IxHash && \
cpanm Time::HiRes && \
cpanm XML::Code && \
cpanm XML::CSV  && \
cpanm XML::Generator && \
cpanm XML::LibXML && \
cpanm XML::LibXML::PrettyPrint && \
cpanm XML::Rabbit && \
cpanm XML::Rabbit::Root && \
cpanm XML::RegExp && \
cpanm XML::Simple && \
cpanm XML::Smart && \
cpanm XML::Tidy && \
cpanm XML::Twig && \
cpanm XML::Writer && \
cpanm YAML


# Archive::Rar : fails test! but is not necessary at all, because 7zip also is able to handle it! 

## ooffice converter - required by monitorcontainr
## installation seems not to terminate... 
## for now: run unoconv from local computer and not on server
#RUN apt-get -y update && \
#apt-get install -y unoconv


## installation failed 2020-01-24 (works on local ubuntu 18-04) !
## cpanm Time::JulianDay && \

### added: String::Diff => as package libstring-diff-perl

## FAILED for the FOLLOWING: 
## cpanm Inline::Python 
## cpanm  RDF::Converter::CSV
## cpanm REST::Client 
##### because dependency failed: Net::SSLeay
###   if you ever need it: failed becuase libssl has to be added: 
## apt-get install libssl-dev

## remove user 'user' before injecting it agin / existing entry for user has to be removed from /etc/shadow with sed 
#RUN sed -i '/^user:\w/d' /etc/shadow && \
#userdel user
## User user does not exist if image is build without docker-tools

#@INJECT_USER@

WORKDIR /home/user

CMD ["bash", "-c", "while : ; do sleep 600 ;done"]
