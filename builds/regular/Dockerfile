# Filename: Dockerfile

FROM node:lts-slim

# Disable Prompt During Packages Installation
ARG DEBIAN_FRONTEND=noninteractive

#Add non-root user, add installation directories and assign proper permissions
RUN mkdir -p /opt/meshcentral

#meshcentral installation
WORKDIR /opt/meshcentral

RUN npm install meshcentral

COPY config.json.template /opt/meshcentral/config.json.template
COPY startup.sh startup.sh
#environment variables

EXPOSE 80 443

#volumes
VOLUME /opt/meshcentral/meshcentral-data
VOLUME /opt/meshcentral/meshcentral-files

CMD ["bash","/opt/meshcentral/startup.sh"]
