# syntax=docker/dockerfile:1

FROM python:3.6.8-slim AS build
WORKDIR /app
ENV PYTHONUNBUFFERED 1
COPY requirements.txt .
RUN pip3 install --user -r requirements.txt

COPY . .
EXPOSE 8000
RUN chmod +x /app/docker-entrypoint.sh

CMD /app/docker-entrypoint.sh
