FROM python:3.11-slim

RUN apt-get update && apt-get install -y libpq-dev gcc
WORKDIR /app
RUN pip install gunicorn==23.0.0
RUN pip install --no-cache-dir psycopg2-binary==2.9.3
COPY requirements.txt .
RUN pip install -r /app/requirements.txt --no-cache-dir
COPY . .
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]
