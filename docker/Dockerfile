# Imagen base de Python
FROM python:3.11-slim

# # Instalar dependencias del sistema
# RUN apt-get update && apt-get install -y \
#     build-essential \
#     && rm -rf /var/lib/apt/lists/*

# Crear directorio de trabajo
WORKDIR /app

# Copiar dependencias
COPY requirements.txt .

# Instalar requerimientos
RUN pip install --no-cache-dir -r requirements.txt

# Copiar el código fuente y recursos
COPY app/ ./app/
COPY datasets/ ./datasets/
COPY images/ ./images/

# Exponer el puerto usado por Streamlit
EXPOSE 8501

# Comando por defecto para iniciar la app
CMD ["streamlit", "run", "app/app.py", "--server.port=8501", "--server.address=0.0.0.0"]
