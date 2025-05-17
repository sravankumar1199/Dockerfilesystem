FROM almalinux:8
ENTRYPOINT ["ping", "-c5", "facebook.com"]
## entrypoint only ping facebook not other so entrypoint is safe ##
## if i give ["ping", "-c5"] our wish to select any like facebook.com and google.com ##
## in docker if i give docker run entry:v2 is not ping but ##

## FORM almalinux:8 
## CMD ["yahoo.com"]
## ENTRYPOINT ["PING", "-c5"] if in case in docker you passed like this  [ docker run entry:v2 ]
## automatic download yahoo 

###### CMD VS ENTRYPOINT ###########
* CMD command can be overridden by any command
* ENTRYPOINT can not be overridden
* you can not overridden ENTRYPOINT, if you try to do it will and append to entrypoint.
* if user is not giving any options ,CMD can supply arguments to ENTRYPOINT
* user can always overridden cmd through terminal