FROM python:3.7.16-slim
RUN apt update && apt install -y gcc cmake libpq-dev python-dev
WORKDIR /app/api_yamdb
COPY api_yamdb/requirements.txt /app
RUN pip3 install --upgrade pip --no-cache-dir
RUN pip3 install -r /app/requirements.txt --no-cache-dir
COPY ../ /app
ENV SECRET_KEY = SECRET_KEY
CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000" ]