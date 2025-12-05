FROM python:3.11-slim

WORKDIR /app

# Instalar dependencias del sistema
RUN apt-get update && apt-get install -y \
    gcc \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

# Copiar requirements.txt (desarrollo, CON django-browser-reload)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copiar el proyecto
COPY . .

# Exponer puerto
EXPOSE 8000

# Comando para desarrollo
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
