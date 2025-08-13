
FROM python:3.11-alpine

WORKDIR /app

EXPOSE 8000

HEALTHCHECK --interval=30s --timeout=3s CMD ["bin/sh", "-c", "curl -f http://localhost:8000/ || exit 1"]

CMD ["python", "-m", "http.server", "8000"]