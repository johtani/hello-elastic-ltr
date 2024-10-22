ARG VARIANT=3.11-bookworm
FROM mcr.microsoft.com/devcontainers/python:${VARIANT}

ENV PYTHONUNBUFFERED 1
ENV TZ Asia/Tokyo

RUN apt update

RUN pip install --upgrade pip
RUN pip install poetry
RUN poetry config virtualenvs.in-project true

WORKDIR /workspace

COPY ../pyproject.toml /workspace
COPY ../notebooks /workspace

RUN poetry install --no-root
