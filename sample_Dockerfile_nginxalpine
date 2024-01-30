FROM nginx:alpine as builder
RUN apk update \
    && apk upgrade \
    && apk add --update --no-cache git
RUN git clone https://github.com/iann0036/former2.git 


FROM nginx:alpine as stage
RUN apk update \
    && apk upgrade 
COPY --from=builder /former2 /usr/share/nginx/html


FROM nginx:alpine
COPY --from=stage / /

#docker build -t former2 .
#docker container run --name former2 --detach --publish 5000:80 former2:latest
