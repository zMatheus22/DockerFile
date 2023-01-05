# DockerFile

Comandos basícos de Docker utilizando a Imagem do NODE.js do Docker Hub: https://hub.docker.com

<hr>

# Imagem do Docker Hub
FROM node

# Cria a pasta no container
WORKDIR /usr/src/app

# Copia tudo o que esta na arquivo package.json e o '.' serve para salva este arquivo na pasta informada no 'WORKDIR' (/usr/src/app)
COPY package.json .

# Roda o comando 'npm install' para instalar todas as dependencias do projeto
RUN npm install

# Copia todos os arquivos do projeto (index.js, app.js, style.css etc.) e salva na pasta do 'WORKDIR' (/usr/src/app)
COPY . .

# Expone a porta do Docker para o acessar
EXPOSE 3000

# Comando para rodar a aplicação
CMD [ "node", "index.js" ]

# Terminal
Agora vá até o terminal do vsCode e rode o segunte comando `docker build .` (o '.' serve para informar que esta pasta tem o arquivo 'Dockerfile')

Agora rodar criar um container com esta imagem criada comando: `docker run 'PORT':'PORT' -d (não abrir o terminal) 'ID_IMAGE' --name 'Nome_do_Container'`

                                                               `docker run 3000:3000 -d 2918a49e22892bb --name Container_Node` 
