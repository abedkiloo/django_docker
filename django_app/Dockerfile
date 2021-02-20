FROM python:3.8.3-alpine


#  my work directory
WORKDIR /usr/src/app

#  environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

#  psycopg2 dependencies
RUN apk update \
    && apk add postgresql-dev gcc python3-dev musl-dev

RUN pip3 install --upgrade pip
COPY ./requirements.txt .
RUN pip3 install -r requirements.txt

#  entrypoint
COPY ./entrypoint.sh .

COPY . .

#run entrypoint
ENTRYPOINT ["/usr/src/app/entrypoint.sh"]
