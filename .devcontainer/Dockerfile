FROM mcr.microsoft.com/devcontainers/python:1-3.11-bullseye

# Instala SQLite
RUN apt-get update && apt-get install -y sqlite3 libsqlite3-dev

# Verifica la versión de SQLite
RUN sqlite3 --version
