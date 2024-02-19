ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

RUN apk add --no-cache git npm

COPY . /
RUN chmod a+x /run.sh
RUN chmod a+x /finish.sh

#RUN cd /Baileys && npm install -force && cd ../ && npm install -force
RUN npm install express --save
RUN cd /Baileys
RUN npm i -f
RUN cd ../
RUN npm i -f

EXPOSE 3000
CMD [ "/run.sh" ]