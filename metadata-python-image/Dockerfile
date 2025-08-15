FROM python:3.11-alpine

ARG APP_VERSION=1.0.0

LABEL maintainer="example@gmail.com" \
      org.opencontainers.image.title="Python App" \
      org.opencontainers.image.description="Python app that prints a message" \
      org.opencontainers.image.version="$APP_VERSION"

COPY app.py .

CMD ["python", "app.py"]