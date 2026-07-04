FROM nginx:alpine

# Build arguments untuk data personal
ARG NAMA
ARG NIM
ARG PRODI
ARG KAMPUS
ARG MINAT
ARG ALASAN
ARG CITA

# Salin file HTML/CSS asli (tidak diubah manual)
COPY html/ /usr/share/nginx/html/

# Ganti semua placeholder secara otomatis saat build
# Delimiter "#" dipakai karena ALASAN/CITA berupa kalimat panjang
# yang mungkin mengandung karakter "/"
RUN sed -i \
    -e "s#NAMA_PLACEHOLDER#${NAMA}#g" \
    -e "s#NIM_PLACEHOLDER#${NIM}#g" \
    -e "s#PRODI_PLACEHOLDER#${PRODI}#g" \
    -e "s#KAMPUS_PLACEHOLDER#${KAMPUS}#g" \
    -e "s#MINAT_PLACEHOLDER#${MINAT}#g" \
    -e "s#ALASAN_PLACEHOLDER#${ALASAN}#g" \
    -e "s#CITA_PLACEHOLDER#${CITA}#g" \
    /usr/share/nginx/html/index.html

EXPOSE 80

