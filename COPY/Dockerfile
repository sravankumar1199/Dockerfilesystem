FROM nginx
## removing default html file ##
RUN rm -rf /usr/share/nginx/html/index.html
## files should be avaviable in currnet directory, when dockerfile exist ##     
COPY index.html /usr/share/nginx/html/index.html  