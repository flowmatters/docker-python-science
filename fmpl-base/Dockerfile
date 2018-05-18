FROM flowmatters/jupyter-spatial

COPY requirements.txt /home/jovyan/requirements_fmpl.txt

USER jovyan

RUN  pip install -r /home/jovyan/requirements_fmpl.txt

CMD start.sh jupyter lab --port=22222
