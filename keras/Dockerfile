FROM tensorflow/tensorflow:latest-py3

RUN apt-get update

RUN pip3 install keras h5py seaborn
RUN pip3 install --upgrade jupyter

RUN apt-get clean
RUN rm -rf /var/lib/apt/lists/* /root/.cache/pip/

WORKDIR /home/work