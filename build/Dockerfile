FROM nvidia/cuda:11.8.0-base-ubuntu20.04

ARG DEBIAN_FRONTEND=noninteractive

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

WORKDIR /app/
COPY requirements.txt /app/

SHELL ["/bin/bash", "-c"]

RUN apt update \
    && apt install -y python3.9 python3.9-dev python3.9-venv  \
    gcc \
    zlib1g-dev \
    wget \
    unzip \
    cmake \
    gfortran \
    libblas-dev \
    liblapack-dev \
    libatlas-base-dev \
    libc-dev build-essential \
    && mkdir /envs/ \
    && python3.9 -m venv /envs/.venv \
    && source /envs/.venv/bin/activate \
    && pip3 install -r /app/requirements.txt
