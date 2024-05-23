# Onlyoffice

## Executando o ONLYOFFICE Document Server

Para executar o ONLYOFFICE Document Server usando Docker, utilize o seguinte comando:

```bash
sudo docker run -i -t -d --restart=always --name onlyoffice-8.0.1 -p 443:443 \
    -e JWT_ENABLED=true \
    -e JWT_SECRET=SUA-SENHA \
    -e JWT_HEADER=AuthorizationJwt \
    -v /app/onlyoffice/DocumentServer/data:/var/www/onlyoffice/Data \
    ghcr.io/mottafcm/onlyoffice/onlyoffice-ilimitado:latest

