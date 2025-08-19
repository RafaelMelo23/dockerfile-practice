#syntax=docker/dockerfile:1
FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .

RUN --mount=type=cache,target=/.cache/pip pip install -r requirements.txt

COPY . .

CMD ["python", "app.py"]