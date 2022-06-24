FROM python:slim-bullseye 

WORKDIR /hello-app

COPY hello.py .

RUN pip install Flask

ENV FLASK_APP=hello

CMD ["flask", "run", "-h", "0.0.0.0"]