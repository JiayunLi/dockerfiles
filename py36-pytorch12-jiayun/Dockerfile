From nvcr.io/nvidia/pytorch:19.11-py3

ARG USER_ID
ARG GROUP_ID

# install opensilde
RUN apt-get update --fix-missing && \
 apt-get install -y python3-openslide &&\
 apt-get install -y tmux && \
 apt-get install -y libaec-dev
 
# activate conda and install packages
RUN pip install spams seaborn scikit-image scikit-learn && \
conda install -c conda-forge tqdm && \
conda install -c conda-forge ipywidgets && \
conda install -c conda-forge libaec && \
conda install opencv pixman=0.36.0 && \
conda install -c pytorch -c fastai fastai && \
pip install h5py lmdb openslide-python==1.1.1 tensorboardX Pillow==6.1.0 tensorboard && \
pip install --upgrade jupyter_client && \
pip install tifffile imagecodecs

RUN if [ ${USER_ID:-0} -ne 0 ] && [ ${GROUP_ID:-0} -ne 0 ]; then \
    groupadd -g ${GROUP_ID} docker-user &&\
    useradd -l -u ${USER_ID} -g docker-user docker-user &&\
    install -d -m 0755 -o docker-user -g docker-user /home/docker-user \
;fi

USER docker-user


