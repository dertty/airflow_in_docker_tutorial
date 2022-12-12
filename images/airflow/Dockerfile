FROM apache/airflow:2.3.4-python3.8
USER root

ENV DEBIAN_FRONTEND noninteractive
ENV TERM linux

RUN chmod -R 1777 /tmp

USER airflow

RUN pip install --upgrade --no-cache-dir pip
RUN pip install --upgrade --no-cache-dir setuptools wheel

RUN pip install --no-cache-dir  \
    apache-airflow-providers-docker  \
    apache-airflow-providers-postgres

WORKDIR /opt/airflow/

COPY requirements.txt requirements.txt
RUN pip install --no-cache-dir -r requirements.txt