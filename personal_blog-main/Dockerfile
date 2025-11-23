
FROM python:3.11-slim


ENV PYTHONUNBUFFERED=1
ENV PIP_DISABLE_PIP_VERSION_CHECK=1

RUN apt-get update && apt-get install -y \
    nodejs \
    npm \
    build-essential \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copiar el proyecto
COPY . .

# Exponer puerto
EXPOSE 8000


CMD ["sh", "-c", "python manage.py migrate && python manage.py runserver 0.0.0.0:8000"]