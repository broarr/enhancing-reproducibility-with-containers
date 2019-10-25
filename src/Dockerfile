FROM python

RUN apt-get update && apt-get install -y \
    libxml2-dev \
    libsqlite3-dev

COPY requirements.txt .
RUN pip install -r requirements.txt

RUN useradd -mUs /bin/bash python \
    && mkdir -p /app \
    && chown -R python:python /app

USER python
WORKDIR /app
COPY . ./

ENTRYPOINT ["python"]
CMD ["my-script.py"]
