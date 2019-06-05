From nvcr.io/nvidia/pytorch:18.06-py3

# install opensilde
RUN apt-get update --fix-missing && \
  apt-get install -y python3-openslide

# COPY envs_py35_pytorch04.yml /tmp
# create new environment
RUN . /opt/conda/etc/profile.d/conda.sh && \
 conda create -y --name=py35 python=3.5 anaconda

# activate conda and instqll packages
RUN . /opt/conda/etc/profile.d/conda.sh && \
 conda activate py35 && \
# too many numpy version: causes conflits
 pip uninstall numpy -y && \
 pip uninstall numpy -y && \
 pip install numpy && \
 conda install pytorch=0.4.1 torchvision=0.2.1 -y  && \
 conda install h5py scikit-image=0.14.0 scikit-learn=0.20.0 \
 scipy=1.1.0 opencv=3.4.1 && \
 jupyter=1.0.0 joblib=0.13.2 && \
 pip install openslide-python==1.1.1 lmdb numpy gpustat  && \
 pip install tensorflow-gpu==1.8.0

# RUN .  /opt/conda/etc/profile.d/conda.sh && \
RUN  echo ". /opt/conda/etc/profile.d/conda.sh" >> ~/.bashrc && \
 echo "conda activate py35" >> ~/.bashrc

