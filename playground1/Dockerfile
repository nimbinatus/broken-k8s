FROM python:alpine
RUN python3 -m ensurepip
RUN pip3 install --upgrade pip \
  && pip3 install virtualenv

RUN adduser -D -g "" -u 1000 starterbase
RUN mkdir -p /base /venv /usr/base
RUN chown -R starterbase:starterbase /base /venv
ENV PYTHONPATH /base

RUN virtualenv /venv
ENV PATH /venv/bin:${PATH}

COPY ./requirements.txt /base/requirements.txt
RUN pip3 install -r /base/requirements.txt
COPY . /base

VOLUME /usr/base
WORKDIR /base

USER starterbase

EXPOSE 5000

CMD ["python3", "-m", "app"]