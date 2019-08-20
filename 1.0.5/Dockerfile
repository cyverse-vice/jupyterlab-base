FROM jupyter/datascience-notebook:latest
COPY jupyter_notebook_config.json /opt/conda/etc/jupyter/jupyter_notebook_config.json

USER root

RUN apt-get update \
    && apt-get install -y libpq-dev lsb wget gnupg apt-transport-https python3.6 python-requests curl \
    && apt-get clean \
    && rm -rf /usr/lib/apt/lists/* \
    && fix-permissions $CONDA_DIR

RUN wget -qO - https://packages.irods.org/irods-signing-key.asc | apt-key add - \
    && echo "deb [arch=amd64] https://packages.irods.org/apt/ xenial main" > /etc/apt/sources.list.d/renci-irods.list \
    && apt-get update \
    && apt-get install -y irods-icommands \
    && apt-get clean \
    && rm -rf /usr/lib/apt/lists/* \
    && fix-permissions $CONDA_DIR

RUN pip install ipython-sql jupyterlab==1.0.5 jupyterlab_sql psycopg2 \
    && conda update -n base conda \
    && conda install -c conda-forge nodejs \
    && jupyter serverextension enable jupyterlab_sql --py --sys-prefix \
    && jupyter lab build

# install the irods plugin for jupyter lab
RUN pip install jupyterlab_irods==3.0.1 \
    && jupyter serverextension enable --py jupyterlab_irods \
    && jupyter labextension install ijab@3.0.1

# install jupyterlab hub-extension, lab-manager, bokeh, google-drive
RUN jupyter lab --version \
    && jupyter labextension install @jupyterlab/hub-extension \
                                    @jupyter-widgets/jupyterlab-manager \
                                    jupyterlab_bokeh \
                                    @jupyterlab/google-drive
USER jovyan

COPY entry.sh /bin
RUN mkdir -p /home/jovyan/.irods

ENTRYPOINT ["bash", "/bin/entry.sh"]
