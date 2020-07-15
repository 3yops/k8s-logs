FROM node
RUN useradd node_user
USER node_user
EXPOSE 3000
ADD src/ /var/node_user
WORKDIR /var/node_user
RUN npm install
CMD ./bin/www

#------------------------

FROM centos:latest
RUN mkdir -p ~/new-dir1
RUN useradd -ms /bin/bash svj
USER svj
RUN mkdir -p ~/new-dir2
RUN mkdir -p /etc/myconf
RUN echo "Some confi data" >> /etc/myconf/my.conf

#===============================

FROM centos:latest
VOLUME [ "/data" ]
RUN echo "Some confi data" >> /data/myconf/my.conf

#======================

FROM nginx:latest
RUN mkdir -p ~/susu
ADD susjadhav/ /
COPY /tmp/susu/ /var/www
WORKDIR /var/www
EXPOSE 80
CMD ./var/www

#==================================

FROM nginx
EXPOSE 80
ADD src/ /usr/share/nginx/html
WORKDIR /usr/share/nginx/html
CMD ./usr/share/nginx/html

#============================

FROM node
ENV NODE_ENV="production"
ENV PORT=3001
RUN mkdir -p /var/node
ADD src/ /var/node
WORKDIR /var/node
RUN npm install
EXPOSE $PORT
ENTRYPOINT ./bin/www
