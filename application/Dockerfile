FROM python:3.12

RUN mkdir /application

RUN pip install pipenv

COPY ./Pipfile /application
COPY ./Pipfile.lock /application
RUN pipenv install
ENV HOME=/application
WORKDIR /application

COPY . /application

ADD docker_wait /wait
RUN chmod +x /wait
CMD /wait
