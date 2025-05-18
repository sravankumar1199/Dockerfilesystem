###### Bare metal servers
* old and days we had to use bare metal servers
* Bare metal server usually has more resources. usually these servers were not shared among projects because of security. we need to buy the server,installOS,supply power and network connecations,physical space,cooling etc.Provisioning time of the server is very high.

### what is docker 
* Now we are using microserver for roboshop project
* In microservers roboshop project divided into types like user,cart,catalogue,payments,shipping so that's why we using images and containers so we no need long servers
* docker and kubernetes is best playform for using microservers
* Ex VM is ec2 and inside VM hypervisor is Docker and inside VM can run multiple containers and all containers and server data stores in VM is ec2

### later VM virtual machines
* virtual machine is a revolutionary technology back in time from the perspective of applications.Entire cloud computing VM's are based of virtualization.

## vm architecture 
* In our loptops we are using different operations systems like ubuntu,centos using because of hypervisor
* VM is aws EC2 is a virtual machine
* inside loptop if we install hypervisor then our loptop runs all operations systems like ubuntu virtual machine ,centos virtual machine 
* inside virtual machine we can multiple containers
* virtual machine means inside physical server we has hypervisor it can run multiple virtual machines
* old and days we have cart has one vm and catalogue has one vm but now a days inside vm we have container like cart has one container,catalogue has one container
* container everything in image format
* image nothing but OS, application runtime,package requirement,and application
* for example centos in ami it is long and centos in docker image it is light

## Installing Docker in server
* create instance in aws console
* google search centos install docker, which favour you are using like redhat,linux so search in google
* copy server ip and login into superputty
######## install docker in server
* sudo su -
* sudo yum install -y yum-utils
* sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
* sudo yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
* sudo systemctl start docker
* sudo systemctl enable docker
* after installed docker then docker group also installed so you need to add user to group
command is 
* sudo usermod -aG docker centos ## centos is user so which user you installed you give that user
* exit and again login in superputty
* docker ps 
* docker images means it shows list of images in server

## dockerhub search in google here you get images but these images created someone
* docker pull nginx ## nginx means image ## if i want to install version so docker pull nginx:perl
docker.io means docker hub
* docker images 

## container means when you run images you get container # conatainer is run image of the instance
######## creating container ##########
* docker create imageid  # docker ps means only running container it shows # all container docker ps -a
* docker start containerid ## means starts container 
* docker stop containerid ## means stops conatainer
* docker run image-id ## pull image,create,start 

## After installed and started nginx container so how to access using port forwording ##
* Every server and container have 0 to 65535 ports
* vm throug forwarding port to container
* inside server it has port interface you can select any number but container what image you installed in container you give that number like 90 is interface and 80 is nginx number
* server public ip and 80 means nginx ## 223.36.225./80 
* first request send to hostport and hostport sends to container port and container sends requests to hostport

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
* To remove the container.if it is running [ docker rm -f [container-id] ] or docker rm [container-id] 
* To remove images = docker rmi [imd-id]
* docker run -d -p <host-port>:<container-port>: image name
* 
* [ docker exec -it container-id bash ] means enter into the container 
* [ docker run image-id sleep 100 ] after 100 seconds container stops
* [ docker run -d image-id sleep 100 ] -d means it runs background 100 seconds its stops
* [ docker exec -it df6a4f4v4af464f4a4 bash ] you can enter into container before 100 seconds but after runs sleep command you ger id and paste it in before of bash
* docker run -d -p 9000:80 imaged-id  ## 
* [ docker build -t add:v1 . ] creating image 
* [ docker exec -it container-id bash ] entering into container ## cd /tmp/,ls -l,sunny.txt this is into the container
* docker run sunny:v2 google.com
* docker inspect [image-d] means shows the information about imagee
* docker run -d -p 9999:80 image-id
* docker rm -f 'docker ps -a -q' ## removing all containers
* docker rmi 'docker images -a -q' ## removing all images
* force fully removed [ docker rmi -f imageid ] -f means force fully removed
* again pulling image from my docker hub account 
command = docker run -d -p 55555:80 sravankumar0099/copy:v1 ## this pull command checks images is in local then it will pull on docker hub 
* docker login and docker logout

### Docker instructions 
* FROM = Create a new build stage from a base image
* RUN = using for create configration and install packages
* CMD = using to start container 
* LABEL = using for tags or filtering perpose it is key value pair ## docker inspect [image-id]
LABEL means if it has 100 images to find perticalar image so that's why we use label and tags ##
LABEL IS = [ docker images --filter label=COURSE=DevOps ]
* EXPOSE = using for example, ## 80/tcp and expose means if someone using your image how they know your image port so that's why we declaring port and using expose instration ## 
* ENV = northing but environment instruation ## for example mongodb project mongodb need cart configar that configar we pass through ENV like key and value format.
* COPY = it is same like variables means but create copy folder inside folder create file like dockerfile, index.html and  configar in index.html file and copy to dockerfile file in copy directroy.
* ADD = ADD is same like COPY but ADD is copy files from github and interet 
* USER = user restrict root access to container and user improve security to containers
* WORKDIR = in workdir directory cd command not works instead of workdir.
so using workdir entering into container terminal direct enter into /tmp directory not /tmp what you mention in workdir directory refer workdir directory.
ARG = [a] it will pass the variables at the build time...[b] example:we have almalinux version 7,8,9,
* interview quention what is the differnt betweent ARG VS ENV
* ARG variables only work in build time,but ENV variables can work in build as well as runtime in container once refer in ENV AND ARG directories
* [a] docker build -t arg:v1 . ## it shows error because not provided veriable
like docker build -t arg:v1 --build-arg version=9 . and docker build -t arg:v1 --build-arg version=7 . version changes but same image is called ARG.
* [b] in arg directory passing variables throug env once refer arg directory.
* [c] ARG can run build but ENV can run build time as well as runtime

### ENV instruation 
* configar vsc and push to github nest open docker installed server in superputty then git pull 
* go cd ENV and [ docker build -t env:v1 . ] building images copy images id
* [ docker run image-id env ] it means container run and exists because of using this command 
* instead of using this command its always container is running [ docker run -d -p 8888:80 nginx ]
* for example using [ docker run ubuntu ping google.com ] it always pinging ubuntu package from google.com = hostOS is centos and cantainer-OS is almalinux whenever i used this command 1. docker pull image from docker hub and crates conatainer request goes through google.com
* for example [ docker run ubuntu pinb -c 10 google.com ] it runs 10 packs from google.com and stops
* [ docker run image-id sleep 100 ] after 100 seconds container stops
* [ docker run -d image-id sleep 100 ] -d means it runs background 100 seconds its stops
* [ docker exec -it df6a4f4v4af464f4a4 bash ] you can enter into container before 100 seconds but after runs sleep command you ger id and paste it in before of bash
* [ docker run almalinux ping google.com ] always installing packs means images from google.com it stops ctrl+ c it stops

## COPY INSTRUATION 
* once refer copy directroy 
* copy directroy push to github
* docker installed server open in superputty 
* in server clone copy directory in server and cd copy/, and git pull
* docker build -t copy:v1 . ## docker build ot image-id:vesion . ## means creating images pulling from docker hub
* docker images ## copy image id
* docker run -d -p 9000:80 imaged-id  ## 
* docker ps ## means checking container is running or not
* docker stop container-id ## stoping container
* copy server public ip and paste in new tab like 3.83.145.247:9000
* singel server we can run multiple containers by using different container ports

## ADD annd COPY both are same process but ADD have more features
* ADD its same like a COPY but ADD have little bit more features like copy files and copy internet files from directory github
* create file in copy directory and push to github and pull to docker installed server
* [ docker build -t add:v1 . ] creating image 
* [ docker images ] copy image-id
* [ docker run -d image-id sleep 60 ] ### can enter into container before 60 seconds
* [ docker ps ] all running container and copy container id
* [ docker exec -it container-id bash ] entering into container ## cd /tmp/,ls -l,sunny.txt this is into the container

### ENTRYPOINT 
* entrypoint it is same like COPY instration BUT in entrypoint we are passing like this RUN echo "WELCOME TO DOCKER IT WRITTEN BY SRAVANKUMAR" > /usr/share/nginx/html/index.html
* in CMD instration like docker run -p 80:80 cmd:v1 ping google.com ## But CMD can overridden but ENTRYPOINT can't be overridden that's why ENTRYPOINT is safe
* docker build -t sunny:v2 . 
* docker run sunny:v2 google.com ## entrypoint whatever we have written in vso that only ping in docker

###### CMD VS ENTRYPOINT ###########
* CMD command can be overridden by any command
* ENTRYPOINT can not be overridden
* you can not overridden ENTRYPOINT, if you try to do it will and append to entrypoint.
* if user is not giving any options ,CMD can supply arguments to ENTRYPOINT
* user can always overridden cmd through terminal

## USER 
* created file in USER directory in vsc but that file is in root user
* Ex every container has root user but if root access so all containers data will manuplati that is not safe that's why USER restrict the root user to images and containers.
** how can you improve the security in docker container = by default docker container gets the root access underline server but we will take care of it we will restrict root access to containers 
* Docker use's vm storage so every container and server data stores in vm's VM means EC2 are there aws servers
* adding user and restricting  root access to containers ##
* refer user and user1 directory

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


## How to access github to server
* Declar in vsc
* push to github
* clone to docker installed server
* go to directroy like cd cmd/ and git pull
* docker build -t sravan:v1 . ## v1 means version
* docker images and copy image id
* docker inspect [image-d] means shows the information about imagee
* docker run -d -p 9999:80 image-id
* docker ps

### How to create docker hub account and pushing files to docker hub and pulling images to server ###
* google search docker hub and create docker hub account 
* [ cd COPY/ ] and [ docker login ] 
* user - sravankumartudi0099 password - 
* docker images
* docker push username/imagename:version means urlname means docker.io
before pushing image to docker hub ## we have to tage the image then its pushed to docker hub
command = docker tag copy:v1 docker.io/sravankumar0099/copy:version
* docker push sravankumar0099/copy:v1 ## images pushes to docker hub
* docker logout 
* docker rm -f 'docker ps -a -q' ## removing all containers
* docker rmi 'docker images -a -q'
force fully removed [ docker rmi -f imageid ] -f means force fully removed
* again pulling image from my docker hub account 
command = docker run -d -p 55555:80 sravankumar0099/copy:v1 ## this pull command checks images is in local then it will pull on docker hub 
* docker stop container-id ## container stops

### DOCKER FLOW INTERVIEW QUENTION ##
* FIRST WRITE A DOCKER FILE
* BUILD IMAGE
* NEXT USING DOCKER RUN AND CREATING IMAGE

### DOCKER ARCHITECTURE
* Docker client means Docker commands
* Docker doemon responsible for managing the lifecycle of containers. Ex= docker daemon checking images in local if not then it pull images from docker hub.
* Docker client interact with docker daemon first checks image from local if not then docker daemon pull image from docker hub and create the image and creates the containers and run
* 

### DOCKER LAYERS 
*  