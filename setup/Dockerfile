FROM jupyter/minimal-notebook:lab-3.6.1

USER root
RUN set -x \
    && apt-get update \
    && apt-get install -y curl postgresql-client

WORKDIR /etc/glances
COPY setup/config_system.py /etc/glances/config_system.py

# setup package, enable classic extension, build lab extension
# USER "${NB_USER}"
RUN mamba install -q -c conda-forge -y uwsgi simple-websocket psycopg
RUN python3 -m pip install glances
RUN fix-permissions /opt/conda

WORKDIR "${HOME}/jupyter-glances-proxy"
COPY . .
RUN python3 -m pip install "${HOME}/jupyter-glances-proxy"
RUN fix-permissions /opt/conda

WORKDIR "${HOME}"
# RUN python3 -m pip install git+https://github.com/huntdatacenter/jupyter-glances-proxy.git
RUN jupyter serverextension enable --sys-prefix jupyter_server_proxy
RUN jupyter labextension disable "@jupyterlab/apputils-extension:announcements"

# copy configs, update permissions as root
USER root
RUN rm -rf "${HOME}/jupyter-glances-proxy"
RUN cp /etc/jupyter/jupyter_notebook_config.py /etc/jupyter/jupyter_notebook_config_base.py
COPY setup/jupyter_notebook_config.py /etc/jupyter/jupyter_notebook_config.py
RUN fix-permissions /etc/jupyter


USER "${NB_USER}"
