ARG version
FROM almalinux:${version}
RUN echo "version passed by user is: ${version}"


## for example: we are creating image that is almalinux version 8 after version 9 we need to use version 9 then without changing image to use ARG instruatin to change version to same image ## 
## FROM almalinux:${version-8} this is default ## if use docker build -t arg:v1 . then its run default version ##
## FORM almalinux:${version} use ## docker build -t arg:v1 --build-arg version=9 . then its download version=8 this is not default ##


## not version also pass variables ##
ARG version
FROM almalinux:${version:-8}
ARG COURSE
ARG TRAINER
RUN echo "course is: ${COURSE}, trainer is: ${TRAINER}"
## docker build -t arg:v1 --build-arg COURSE=DEVOPS --build-arg TRAINER=SRAVAN ##

### INTERVIEW QUENTIONS 
# what is ARG VS ENV
# ARG varibles work in build time but ENV variables can work build time and as well as runtime.

### Enter into container type env
# enter env ## env means to showes inside the container


####
ARG version
FROM almalinux:${version:-9}
ARG COURSE
ARG TRAINER
ENV COURSE=${COURSE}
ENV TRAINER=${TRAINER}
RUN echo "course is: ${COURSE}, trainer is: ${TRAINER}"
## docker build -t arg:v1 --build-arg COURSE=DevOps --build-arg TRAINER=SRAVAN .

## arg can run build and env can run build and runtime
## but using env couse=${course} this variables passing throught env to the inside arg container
## use this command in docker 
# docker build -t arg:v1 --build-arg COURSE=Devops --build-arg TRAINER=sravan .
# docker exec -it arg:v1 bash 
# enter [ env ] to apperes all variables inside the container