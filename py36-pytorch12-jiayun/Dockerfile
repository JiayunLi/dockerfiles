From nvcr.io/nvidia/pytorch:19.06-py3

ARG USER_ID
ARG GROUP_ID

# install opensilde
RUN apt-get update --fix-missing && \
  apt-get install -y python3-openslide

# activate conda and install packages
RUN pip install spams && \
conda install -c conda-forge tqdm && \
conda install opencv && \
pip install h5py lmdb openslide-python==1.1.1 tensorboardX

RUN if [ ${USER_ID:-0} -ne 0 ] && [ ${GROUP_ID:-0} -ne 0 ]; then \
    groupadd -g ${GROUP_ID} docker-user &&\
    useradd -l -u ${USER_ID} -g docker-user docker-user &&\
    install -d -m 0755 -o docker-user -g docker-user /home/docker-user \
;fi

USER docker-user
