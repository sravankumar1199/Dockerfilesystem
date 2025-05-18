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