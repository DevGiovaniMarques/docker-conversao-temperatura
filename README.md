# docker-conversao-temperatura
O projeto conversão de temperatura é um projeto desenvolvido em NodeJS. O projeto tem como objetivo ser um exemplo para a criação de ambiente com containers usando NodeJS.

Primeiro para para criação foi fazer um clone do repositorio original: https://github.com/KubeDev/conversao-temperatura

Após isso devemos criar o arquivo Dockerfile para fazer o build da imagem em docker.

```
FROM node
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 8080
CMD ["node", "server.js"]
```

Após criar o arquivo Dockerfile com os comandos acima, vamos fazer o build da image, executando o comando no terminal no caminho que esteja o arquivo Dockerfile
```
 docker image build -t conversao-temperatura .
```

Depois pode executar o comando para lista a imagem criada:
```
docker image ls
```

Agora vai criar o container para rodas a aplicação:
```
docker container run -d -p 8080:8080 conversao-temperatura
```
Para verificar se o container já está rodando execute o comando:
```
docker container ls
```

Para ver a aplicação rodando na porta 8080, ou a que você definir, no meu caso estará rodando local

```
http://localhost:8080/
```




