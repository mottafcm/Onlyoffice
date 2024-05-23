# Onlyoffice

## Executando o ONLYOFFICE Document Server

### Crie a pasta e certificados

```bash
mkdir -p /app/onlyoffice/DocumentServer/data/certs && \
openssl genrsa -out /app/onlyoffice/DocumentServer/data/certs/tls.key 2048 && \
openssl req -new -key /app/onlyoffice/DocumentServer/data/certs/tls.key -out /app/onlyoffice/DocumentServer/data/certs/tls.csr && \
openssl x509 -req -days 365 -in /app/onlyoffice/DocumentServer/data/certs/tls.csr -signkey /app/onlyoffice/DocumentServer/data/certs/tls.key -out /app/onlyoffice/DocumentServer/data/certs/tls.crt

```bash


Para executar o ONLYOFFICE Document Server usando Docker, utilize o seguinte comando:

```bash
sudo docker run -i -t -d --restart=always --name onlyoffice-8.0.1 -p 443:443 \
    -e JWT_ENABLED=true \
    -e JWT_SECRET=SUA-SENHA \
    -e JWT_HEADER=AuthorizationJwt \
    -v /app/onlyoffice/DocumentServer/data:/var/www/onlyoffice/Data \
    ghcr.io/mottafcm/onlyoffice/onlyoffice-ilimitado:latest

