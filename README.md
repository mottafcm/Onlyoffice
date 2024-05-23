# Onlyoffice

Execute o comando assim:

sudo docker run -i -t -d --restart=always --name onlyoffice-8.0.1 -p 443:443 \
-e JWT_ENABLED=true \
-e JWT_SECRET=E#72wao*n45r \
-e JWT_HEADER=AuthorizationJwt \
-v /app/onlyoffice/DocumentServer/data:/var/www/onlyoffice/Data  onlyoffice/documentserver
