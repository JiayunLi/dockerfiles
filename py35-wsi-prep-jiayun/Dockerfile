From continuumio/anaconda
# install opensilde
RUN apt-get update --fix-missing && \
  apt-get install -y python3-openslide && \
  apt-get install -y gcc

# create new environment
RUN . /opt/conda/etc/profile.d/conda.sh && \
 conda create -y --name=py35 python=3.5 anaconda

# activate conda and instqll packages
RUN . /opt/conda/etc/profile.d/conda.sh && \
 conda activate py35 && \
 conda install h5py scikit-image=0.14.0 scikit-learn=0.20.0 \
 scipy=1.1.0 opencv=3.4.1 && \
 jupyter=1.0.0 && \
 pip install openslide-python==1.1.1 lmdb && \
 conda install -c conda-forge python-spams -y 

RUN apt update && \
apt install -y  libgl1-mesa-glx

RUN  echo ". /opt/conda/etc/profile.d/conda.sh" >> ~/.bashrc && \
 echo "conda activate py35" >> ~/.bashrc
