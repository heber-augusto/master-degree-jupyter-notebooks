# Choose your desired base image
FROM jupyter/scipy-notebook:2c80cf3537ca

USER root

# install
RUN apt-get update \
    && apt-get clean \
    && apt-get install wget \
    && apt-get clean \
    && apt-get install libaio1 \
    && apt-get clean \
    && mkdir -p /opt/oracle \
    && cd /opt/oracle/ \
    && wget https://download.oracle.com/otn_software/linux/instantclient/19600/instantclient-basiclite-linux.x64-19.6.0.0.0dbru.zip \
    && unzip instantclient-basiclite-linux.x64-19.6.0.0.0dbru.zip \
    && export LD_LIBRARY_PATH=/opt/oracle/instantclient_19_6:$LD_LIBRARY_PATH \
    && rm instantclient-basiclite-linux.x64-19.6.0.0.0dbru.zip


USER $NB_UID

#ENTRYPOINT ["jupyter", "notebook"]