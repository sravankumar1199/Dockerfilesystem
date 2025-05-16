FROM almalinux:8
RUN yum install nginx -y
## expose is not adding any functionlity,it is just for information ##
EXPOSE 80/tcp
CMD ["nginx" "-g", "daemon off;" ]
## 80/tcp means if someone using your image how they know your image port so that's why we declaring port and using expose instration ## 