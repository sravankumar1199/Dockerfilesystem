###### Bare metal servers
* old and days we had to use bare metal servers
* Bare metal server usually has more resources. usually these servers were not shared among projects because of security. we need to buy the server,installOS,supply power and network connecations,physical space,cooling etc.Provisioning time of the server is very high.

### what is docker 
* Now we are using microserver for roboshop project
* In microservers roboshop project divided into types like user,cart,catalogue,payments,shipping so that's why we using images and containers so we no need long servers
* docker and kubernetes is best playform for using microservers

### later VM virtual machines
* virtual machine is a revolutionary technology back in time from the perspective of applications.Entire cloud computing VM's are based of virtualization.

## vm architecture 
* In our loptops we are using different operations systems like ubuntu,centos using because of hypervisor
* inside loptop if we install hypervisor then our loptop runs all operations systems like ubuntu virtual machine ,centos virtual machine 
* inside virtual machine we can multiple containers
* virtual machine means inside physical server we has hypervisor it can run multiple virtual machines
* old and days we have cart has one vm and catalogue has one vm but now days inside vm we have container like cart has one container,catalogue has one container
* container everything in image format
* image nothing but OS, application runtime,package requirement,and application
* for example centos in ami it is long and centos in docker image it is light
## Installing Docker in server
* create instance in aws console
* google search centos install docker, which favour you are using like redhat,linux so search in google
* copy server ip and login into superputty
######## install docker in server
[a] sudo su -
[b] sudo yum install -y yum-utils
[c] sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
[d] sudo yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
[e] sudo systemctl start docker
[f] sudo systemctl enable docker
[g] exit
[h] after installed docker then docker group also installed so you need to add user to group
command is 
[*] sudo usermod -aG docker centos ## centos is user so which user you installed you give that user
[i] exit and again logout and login in superputty
[j] docker ps 
[k] docker images means it shows list of images in server
## dockerhub search in google here you get images but these images created someone
* docker pull nginx ## nginx means image ## if i want to install version so docker pull nginx:perl
docker.io means docker hub
* docker images 
## container means when you run images you get container # conatainer is run image of the instance
######## creating container
* docker create imageid  # docker ps means only running container it shows # all container docker ps -a
* docker start containerid ## means starts container 
* docker stop containerid ## means stops conatainer
## After installed started nginx container so how to access using port forwording ##
* Every server and container have 0 to 65535 ports
* vm throug forwarding port to container
* inside server it has port interface you can select any number but container what image you installed in container you give that number like 90 is interface and 80 is nginx number
* server public ip and 80 means nginx ## 223.36.225./80 
* first request send to hostport and hostport sends to container port and container sends requests to hostport
## docker run ## pull image,create,start ##

### docket commands 
* To display the available images = docker images
* To pull the image from docker hub. if you mention version it will pull the latest version by default = docker pull <image-name>:version
* To create container out of image = docker create imageid
* To display running containers = docker ps
* To display all the containers = docker pa -a
* To start container = docker start container-id
* To pull,create and start the container with single command = docker run <image-name>:version
* By default docker containers run in the background attach to the screen = docker run -d [image:name]:[version]
* To stop container = docker stop containerid
* To remove the container.if it is running docker rm -f [container-id] or docker rm [container-id] 
* To remove images = docker rmi [imd-id]
* docker run -p <host-port>:<container-port>: image name

### Docker instructions 
* FROM = Create a new build stage from a base image
* RUN = using for create configration and install packages
* CMD = using to start container 
* LABEL = using for tags or filtering perpose it is key value pair ## docker inspect [image-id]
LABEL means if it has 100 images to find perticalar image so that's why we use label and tags ##
LABEL IS = docker images --filter label=COURSE=DevOps
*

### what is virtual machines and virtualization 
* vm is ubuntu and centos,aws linux, mocOS these are VMs
* virutualization is one laptop two operation systems running like windows and ubuntu is called virutualization.

### Dockerfile
Dockerfile is declarative way for creating images.
we can build the images and we can push to any docker repository.
* FROM is declaration
* RUN is configration and installing packages
* CMD is starts for the image like nginx  ## whenever cmd starts images that time container creates automaticlly
####### interview question is what is the different between run and cmd or from and run ? ###

## create github repo 
* Push docker folder to github
* clone to docker installed server ## git clone and git pull


## How build docker image

[a] docker build -t image-name:version . ## [.] means current directory
docker build -t cmd:nginx .


## How to access nginx in server 
* docker run -p 9999:80 fe33cb7f7039 
* using this command docker run -p 9999:80 imageid of nginx

