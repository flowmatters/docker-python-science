FROM jupyter/datascience-notebook

COPY requirements.txt /home/jovyan/requirements.txt

USER root

RUN mkdir /home/jovyan/temp && \
    cd /home/jovyan/temp && \
    wget 'http://download.osgeo.org/gdal/2.3.0/gdal-2.3.0.tar.gz' && \
    tar xzf gdal-2.3.0.tar.gz && \
    cd gdal-2.3.0 && \
    ./configure && make && make install

USER jovyan

RUN  pip install -r /home/jovyan/requirements.txt

CMD start.sh jupyter lab --port=22222
