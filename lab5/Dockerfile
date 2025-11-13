FROM jupyter/datascience-notebook:latest

USER root

# Установка системных зависимостей (если нужны)
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    build-essential \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Копирование requirements файла
COPY requirements.txt /tmp/requirements.txt

# Установка Python пакетов
RUN pip install --upgrade pip && \
    pip install -r /tmp/requirements.txt && \
    rm /tmp/requirements.txt

# Возвращаемся к пользователю jovyan
USER ${NB_UID}