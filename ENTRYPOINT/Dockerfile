FROM almalinux:8
RUN yum install nginx -y
## removing default index.html and againg creating index.html file inside html directory ##
RUN rm -rf /usr/share/nginx/html/index.html
RUN echo "WELCOME TO DOCKER IT WRITTEN BY SRAVANKUMAR" > /usr/share/nginx/html/index.html
ENTRYPOINT ["nginx", "-g", "daemon off;"]
### CMD means command ###
### daemon off means other images and packs not installed like google.com ##