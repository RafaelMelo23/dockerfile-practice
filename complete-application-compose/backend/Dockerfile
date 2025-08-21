
FROM python:3.11-slim as builder

WORKDIR /app

RUN python -m venv /opt/venv

COPY backend/requirements.txt .

RUN /opt/venv/bin/pip install --no-cache-dir -r requirements.txt

COPY backend/app/ .

FROM gcr.io/distroless/python3-debian11

ENV PATH="/opt/venv/bin:$PATH"
WORKDIR /app

COPY --from=builder /app/opt/venv /app/opt/venv
COPY --from=builder /app .

USER nonroot

EXPOSE 5000

CMD ["gunicorn", "bind--", "0.0.0.0:5000", "app:app"]






