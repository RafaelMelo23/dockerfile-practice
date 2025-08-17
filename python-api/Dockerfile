
FROM python:3.11-alpine

ARG PORT=8000
ENV PORT=${PORT}
ENV PYTHONUNBUFFERED=1

RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/* \
    && adduser -D appuser

WORKDIR /app

COPY --chown=appuser:appuser requirements.txt .
COPY --chown=appuser:appuser app/ .

RUN pip install --no-cache-dir -r requirements.txt

USER appuser

EXPOSE ${PORT}

HEALTHCHECK --interval=30s --timeout=5s --retries=5 CMD ["/bin/sh", "-c", "curl -f http://localhost:${PORT}/health || exit 1"]

ENTRYPOINT ["gunicorn"]
CMD ["main:app", "bindhost", "0.0.0.0:${PORT}"]

