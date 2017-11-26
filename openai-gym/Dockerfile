FROM tensorflow/tensorflow:latest-py3

RUN apt-get update

RUN add-apt-repository ppa:george-edison55/cmake-3.x && \
    apt-get install -y cmake && \
    apt-get upgrade -y


RUN pip3 install keras h5py seaborn
RUN pip3 install --upgrade jupyter

# RUN apt-get install -y \
#     xorg-dev \
#     libglu1-mesa libgl1-mesa-dev \
#     xvfb \
#     libxinerama1 libxcursor1

# RUN apt-get install -y libgtk-3-dev
# RUN pip3 install GObject cffi cairocffi

RUN apt-get install -y xvfb python-opengl
RUN pip3 install gym

RUN apt-get clean
RUN rm -rf /var/li/apt/lists/* /root/.cache/pip/

COPY ./run_jupyter.sh /opt/
RUN chmod +x /opt/run_jupyter.sh

WORKDIR /home/work

COPY ./sample.ipynb sample.ipynb

CMD ["/opt/run_jupyter.sh"]