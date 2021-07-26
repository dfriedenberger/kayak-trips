FROM tensorflow/tensorflow:latest-jupyter
#FROM tensorflow/tensorflow:latest-gpu-jupyter

RUN apt-get update && apt-get -y install \
             curl \
             wget \
             unzip \
             default-jdk \
             postgresql-client
             
# set timezone to Europ/Berlin
RUN ln -fs /usr/share/zoneinfo/Europe/Berlin /etc/localtime
RUN apt-get install -y tzdata
RUN dpkg-reconfigure -f noninteractive tzdata

RUN pip install --upgrade pip
RUN pip install folium 
RUN pip install geopandas 
RUN pip install sqlalchemy psycopg2
RUN pip install bs4







