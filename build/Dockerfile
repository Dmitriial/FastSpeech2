FROM nvidia/cuda:11.8.0-base-ubuntu20.04

ARG DEBIAN_FRONTEND=noninteractive

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

WORKDIR /app/
COPY . /app/

RUN apt update \
    && apt install -y python3.9 python3.9-venv \
    && mkdir /envs/ \
    && cd /envs/ \
    && python3.9 -m venv .venv \
    && cd /app/ \
    && source /envs/.venv/bin/activate \
    && pip install -r requirments.txt
