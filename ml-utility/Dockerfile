FROM ubuntu:16.04

LABEL maintainer="kosatelim@gmail.com"

RUN apt-get update && apt-get install -y --no-install-recommends \
        build-essential \
        curl \
        pkg-config \
        python3 \
        python-dev python3-dev \
        rsync \
        software-properties-common \
        unzip \
        && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN curl -O https://bootstrap.pypa.io/get-pip.py && \
    python3 get-pip.py && \
    rm get-pip.py

RUN pip3 --no-cache-dir install \
        Pillow \
        h5py \
        ipykernel \
        jupyter \
        matplotlib \
        numpy \
        pandas \
        scipy \
        sklearn \
        seaborn \
        && \
    python3 -m ipykernel.kernelspec

RUN unlink /usr/bin/python
RUN ln -s /usr/bin/python3 /usr/bin/python

# Set up our notebook config.
COPY jupyter_notebook_config.py /root/.jupyter/

# Jupyter has issues with being run directly:
#   https://github.com/ipython/ipython/issues/7062
# We just add a little wrapper script.
COPY run_jupyter.sh /
RUN chmod +x /run_jupyter.sh

EXPOSE 8888

WORKDIR "/notebooks"

CMD ["/run_jupyter.sh", "--allow-root"]
