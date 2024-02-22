FROM debian:bookworm

# Instala las herramientas necesarias para la compilación
RUN apt-get update && apt-get install -y \
    build-essential \
    wget \
    libreadline-dev

# Descarga y compila SQLite desde el código fuente
RUN wget https://www.sqlite.org/2023/sqlite-autoconf-3390200.tar.gz && \
    tar xvfz sqlite-autoconf-3390200.tar.gz && \
    cd sqlite-autoconf-3390200 && \
    ./configure --prefix=/usr --disable-static && \
    make && \
    make install

# Verifica la versión de SQLite
RUN sqlite3 --version

# Continúa con la configuración de tu contenedor...
