FROM almalinux:8
RUN yum install nginx -y
RUN echo "WELCOME TO DOCKER" > /usr/share/nginx/html/sravanfile.html
CMD ["nginx", "-g", "daemon off;"]