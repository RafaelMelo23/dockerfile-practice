FROM python:3.11-alpine

WORKDIR /app

COPY requirements.txt .

RUN apk add jpeg-dev zlib-dev | && pip install --no-cache-dir -r requirements.txt

COPY . .

CMD ["python", "app.py"]