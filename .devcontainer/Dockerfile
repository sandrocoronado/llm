FROM debian:bookworm

# Instala las dependencias necesarias para compilar SQLite
RUN apt-get update && apt-get install -y build-essential curl libreadline-dev

# Descarga el código fuente de SQLite
RUN curl -O https://www.sqlite.org/2021/sqlite-autoconf-3350000.tar.gz \
    && tar xzf sqlite-autoconf-3350000.tar.gz \
    && cd sqlite-autoconf-3350000 \
    && ./configure --prefix=/usr --disable-static CFLAGS="-g -O2 -DSQLITE_ENABLE_FTS5" \
    && make \
    && make install

# Limpieza de archivos temporales y cache
RUN apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* sqlite-autoconf-3350000.tar.gz \
    && sqlite3 --version

