
FROM centos:latest

USER root

WORKDIR /tmp

RUN yum install -y bzip2 wget git \
&& curl https://bootstrap.pypa.io/get-pip.py | python - \
&& pip install 'mlflow==0.2.1' \
&& wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh \
&& mkdir /.conda  \
&& chown -Rv root /.conda \
&& chmod -R ug+rwx /.conda \
&& bash Miniconda3-latest-Linux-x86_64.sh -b -p /tmp/conda 


ENV PATH="/opt/conda/bin:${PATH}"
COPY entrypoint.sh /etc/entrypoint.sh

#USER 1001

EXPOSE 5000
ENTRYPOINT ["/etc/entrypoint.sh"]
