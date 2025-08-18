
FROM python:3.11-slim AS builder

WORKDIR /app

RUN python -m venv /opt/venv

COPY requirements.txt .
RUN /opt/venv/bin/pip install --no-cache-dir -r requirements.txt

COPY . .

FROM gcr.io/distroless/python3-debian11

WORKDIR /app

ENV PATH="/opt/venv/bin:$PATH"

COPY --from=builder /opt/venv /opt/venv
COPY --from=builder /app .

USER nonroot

EXPOSE 5000

CMD ["gunicorn", "--bind", "0.0.0.0:5000", "app:app"]


