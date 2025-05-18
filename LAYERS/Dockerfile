FROM almalinux:8
RUN yum install nginx -y
RUN echo "WELCOME TO DOCKER" > /usr/share/nginx/html/sravanfile.html
RUN yum install git -y
RUN yum install maven -y
CMD ["nginx", "-g", "daemon off;"]