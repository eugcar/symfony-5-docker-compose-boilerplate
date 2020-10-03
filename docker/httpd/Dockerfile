FROM httpd:2.4-alpine

# Remove unused extra configuration files
RUN rm /usr/local/apache2/conf/extra/httpd-mpm.conf && \
    rm /usr/local/apache2/conf/extra/httpd-multilang-errordoc.conf && \
    rm /usr/local/apache2/conf/extra/httpd-autoindex.conf && \
    rm /usr/local/apache2/conf/extra/httpd-languages.conf && \
    rm /usr/local/apache2/conf/extra/httpd-userdir.conf && \
    rm /usr/local/apache2/conf/extra/httpd-info.conf && \
    rm /usr/local/apache2/conf/extra/httpd-manual.conf && \
    rm /usr/local/apache2/conf/extra/httpd-dav.conf && \
    rm /usr/local/apache2/conf/extra/httpd-default.conf && \
    rm /usr/local/apache2/conf/extra/httpd-ssl.conf

# Copy custom configuration files
COPY conf/httpd.conf /usr/local/apache2/conf/httpd.conf
COPY conf/www.conf   /usr/local/apache2/conf/extra/httpd-vhosts.conf