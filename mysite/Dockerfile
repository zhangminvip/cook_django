FROM python:3
ENV PYTHONUNBUFFERED 1
RUN mkdir /webapps
WORKDIR /webapps

COPY sources.list /etc/apt/
# Installing OS Dependencies
#RUN apt-get update && apt-get upgrade -y && apt-get install -y \
#libsqlite3-dev

#RUN pip install -U pip setuptools
#&& pip3 install --upgrade pip

RUN pip install -i https://pypi.tuna.tsinghua.edu.cn/simple -U pip setuptools

COPY requirements.txt  /webapps/
COPY sources.list /etc/apt/
#COPY requirements-opt.txt /webapps/

RUN pip install -i https://pypi.tuna.tsinghua.edu.cn/simple -r /webapps/requirements.txt
#RUN pip install -r /webapps/requirements-opt.txt

ADD . /webapps/

# Django service
EXPOSE 8000