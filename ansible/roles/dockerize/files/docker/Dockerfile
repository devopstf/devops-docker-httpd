FROM centos:centos7

# Visit our organization "devopstf" for more images to come!
LABEL mantainer="odiazdom - devopstf - DevOps Engineering"

RUN yum update -y && \
	yum install -y httpd-2.4.6 && \	
	yum install -y mod_ssl-2.4.6 && \
	groupadd -g 65500 httpd && \
	chgrp -R httpd /var/log/httpd && \
	chmod -R g+rwx /var/log/httpd && \
	chgrp -R httpd /run && \
	chmod -R g+rwx /run && \
	yum clean all

# Expose port 80 & 443... But you can choose what you really want to!	
EXPOSE 80 443

# Copies a simple entrypoint.sh to mantain the container up
COPY entrypoint.sh
RUN chmod +x entrypoint.sh

CMD ["/usr/bin/bash entrypoint.sh"]