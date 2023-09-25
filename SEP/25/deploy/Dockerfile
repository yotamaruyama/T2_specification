FROM python:3

RUN apt-get update && apt-get install -y \
    nano
WORKDIR  /code
COPY requirements.txt /code/
RUN pip install -r requirements.txt

RUN mkdir -p /var/run/gunicorn
CMD ["gunicorn", "T2.wsgi", "--bind=unix:/var/run/gunicorn/gunicorn.sock"]
