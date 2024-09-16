# Projeto Docker

## Landing Page feita em html+css, rodando em python e containerizada em Docker

Este projeto consiste em uma *landing page* desenvoldida em html e css, rododando em python através do frammework "Flask", coitainerizada em docker, criada para a disciplina de Computação em nuvem.

![Tela Principal](/static/landing-page.png)


### Tecnologias Utilizadas

- **Python**: Linguagem de programação principal usada no projeto.
- **Flask**: Framework para desenvolvimento de aplicações web em Python.
- **Docker**: Plataforma utilizada para desenvolver e executar a aplicação em contêiner.
- **HTML/CSS:** Utilizados para criar a estrutura e o estilo visual da página.

### Dockerfile
![Docker File](/static/dockerFile.png)

## Descrição dos comandos

**FROM ubuntu:22.04 :** 
Especifica a imagem base para o contêiner. Neste caso será construído sobre um sistema Ubuntu 22.04.

**RUN apt-get update && \
    apt-get install python3.11 python3.11-dev python3-pip -y :** 
Atualiza a lista de pacotes disponíveis (apt-get update) e instala o Python 3.11, o pacote de desenvolvimento do Python 3.11 e o pip (gerenciador de pacotes do Python) no contêiner. O -y aceita automaticamente todas as solicitações de confirmação, permitindo uma instalação não interativa.

**WORKDIR /app :** 
Define o diretório de trabalho dentro do contêiner para /app. Todos os comandos subsequentes, serão executados a partir deste diretório.

**COPY . . :** 
Copia todos os arquivos e diretórios do diretório atual para o diretório de trabalho do contêiner (/app). 

**RUN pip3 install --no-cache-dir -r requirements.txt :** 
Instala as dependências do Python listadas no arquivo requirements.txt usando o pip. A opção --no-cache-dir evita o armazenamento do cache dos pacotes no contêiner.

**EXPOSE 8080 :** 
Informa ao Docker que o contêiner escutará na porta 8080.

**CMD [ "python3", "app.py" ] :** 
Define o comando padrão a ser executado quando o contêiner for iniciado. Neste caso, o contêiner executará python3 app.py, iniciando a aplicação.

### Rodando o container:

![prompt](/static/prompt.png)
- **1 docker images** Comando executado para provar que a imagem docker foi criada.
- **2**  imagem criada.
- **3 docker run -it -p 8080:8080**  comando para iniciar o conteiner
- **4** print da imagem rodando

## Print do Docker desktop
![docker desktop](/static/docker-desktop.png)

## Print do navegador no endereço 127.0.0.1/8080
![docker desktop](/static/landing-page.png)



por Leonardo Perez
