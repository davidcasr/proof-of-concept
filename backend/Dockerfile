FROM python:3.7.3
ENV PYTHONUNBUFFERED 1
RUN mkdir /code
WORKDIR /code
ADD requirements.txt /code/
RUN apt-get update && apt-get install -y netcat
RUN apt-get install -y binutils libproj-dev gdal-bin
RUN pip install -r requirements.txt
ADD . /code/
EXPOSE 8000

COPY ./docker-entrypoint.sh ./docker-entrypoint.sh
ENTRYPOINT ["./docker-entrypoint.sh"]