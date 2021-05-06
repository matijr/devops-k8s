#Image and main folder
FROM python:3.7-slim-buster
RUN mkdir /backend
WORKDIR /backend

#Environments
ENV DJANGO_SETTINGS_MODULE=backend.settings
ENV ENDPOINT=http://0.0.0.0:8000/api/requests-loan/
ENV SECRET_KEY=7d@1v(esv5f75z=k25(6@md7q4reb$w$j8e2c2o^1w+7rpwgks

#Dependencies
RUN apt-get update \
&& pip3 install --upgrade pip \
&& pip3 install psycopg2-binary \
&& apt-get install libpq-dev -y gcc -y python3-dev -y libgraphviz-dev -y

#Requirements
COPY requirements.txt /backend/requirements.txt
RUN pip3 install -r requirements.txt
EXPOSE 8000

#Copy and commands
COPY . .
CMD [ "python3", "manage.py", "runserver", "0.0.0.0:8000" ]