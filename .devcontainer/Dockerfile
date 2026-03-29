FROM jupyter/datascience-notebook

USER root

ENV SHELL=/bin/bash

# Hack for controlling how chromium works with no-sandbox and allow-downloads
RUN mkdir -p /home/jovyan/.jupyter
COPY .devcontainer/jupyter_lab_config.py /home/jovyan/.jupyter/jupyter_lab_config.py

RUN fix-permissions /home/jovyan/.jupyter

## Install R libraries
USER ${NB_UID}

## Disable NBclassic

RUN jupyter server extension disable nbclassic  

