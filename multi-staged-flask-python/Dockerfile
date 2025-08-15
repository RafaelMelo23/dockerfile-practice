FROM python:3.11-slim AS builder

WORKDIR /app

RUN python -m venv /opt/venv
COPY requirements.txt .

RUN /opt/venv/bin/pip install --no-cache-dir -r requirements.txt

FROM python:3.11-slim

LABEL maintainer="Test" \
      description="FastAPI multi-staged python image"

RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*

RUN adduser -D nonroot

WORKDIR /app

COPY --chown=nonroot:nonroot --from=builder /opt/venv opt/venv
COPY --chown=nonroot:nonroot app/ .
COPY app/ .

USER nonroot

EXPOSE 8080

HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 \
    CMD ["bin/sh", "-c", "curl -f http://localhost:8080 || exit 1"]

ENV PATH="opt/venv/bin:$PATH"


ENTRYPOINT ["uvicorn"]
CMD ["main:app", "--host", "0.0.0.0", "--port 8080"]