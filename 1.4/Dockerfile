# syntax=docker/dockerfile:1

FROM ubuntu:22.04

# Указываем рабочий каталог
WORKDIR /app

# Обновляем список пакетов и Устанавливаем нужные пакеты и чистим кэш.
# Все в одну строку
RUN apt-get update -y --no-install-recommends && \
  apt-get -y install \
  libpq-dev \
  imagemagick \
  gsfonts \
  python3.8 \
  supervisor \
  python-pip && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* 

# Копируем список зависимотей
COPY requirements.txt .

# Устанавливаем зависимости
RUN pip install -r requirements.txt

# Копируем исходный код
COPY . .

# Запускаем скрипт, который запустит все остальное
CMD ["/app/init.sh"]
