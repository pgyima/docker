FROM alpine:3.10.2
LABEL maintainer="Peter Gyima <peter.gyima@gimadigital.com>"

#add curl
RUN apk update
RUN app add curl 

# copy script
COPY entrypoint.sh /bin/entrypoint.sh

# run the script 
ENTRYPOINT ["/bin/entrypoint.sh"]
