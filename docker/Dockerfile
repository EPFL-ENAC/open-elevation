FROM ghcr.io/osgeo/gdal:ubuntu-small-3.7.3

ENV TZ=Europe/Madrid
ENV CPLUS_INCLUDE_PATH=/usr/include/gdal
ENV CINCLUDE_PATH=/usr/include/gdal
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update
RUN apt-get install -y libspatialindex-dev unar bc python3-pip wget 

ADD ./requirements.txt .
RUN pip install -r requirements.txt

RUN mkdir /code
ADD . /code/

WORKDIR /code
CMD ["python3", "server.py"]

EXPOSE 8080

EXPOSE 8443
