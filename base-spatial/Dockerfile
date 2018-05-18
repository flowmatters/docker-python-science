FROM jupyter/datascience-notebook

COPY requirements.txt /home/jovyan/requirements.txt

# python-software-properties

USER root

# RUN apt-get update && \
#     apt-get install -y software-properties-common && \
#     add-apt-repository -y ppa:ubuntugis/ppa && \
#     apt-get update && \
#     apt-get install -y gdal-bin python-gdal python3-gdal

RUN mkdir /home/jovyan/temp && \
    cd /home/jovyan/temp && \
    wget 'http://download.osgeo.org/gdal/2.3.0/gdal-2.3.0.tar.gz' && \
    tar xzf gdal-2.3.0.tar.gz && \
    cd gdal-2.3.0 && \
    ./configure && make && make install

USER jovyan

RUN  pip install -r /home/jovyan/requirements.txt

CMD start.sh jupyter lab --port=22222
