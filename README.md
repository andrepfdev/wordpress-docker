![wordpress-docker](https://github.com/andrepfdev/wordpress-docker/assets/49399742/8f25e1f7-650e-44de-91f8-9d11f854899c)

# WordPress & Docker
**SOBRE A CONFIGURAÇÃO:**

Este repositório contém uma configuração de Docker Compose para um site WordPress completo, com banco de dados MySQL e phpMyAdmin.

Para usar esta configuração, você precisará ter o Docker instalado. Depois de instalar o Docker, você pode clonar este repositório e executar o seguinte comando:

```
docker-compose up -d
```

Este comando irá iniciar todos os contêineres necessários para o seu site WordPress. Você pode então acessar o seu site em `http://localhost:8080`.

**Ambiente**

A configuração do Docker Compose define as seguintes variáveis de ambiente para o contêiner do WordPress:

* `WORDPRESS_DB_HOST`: O nome do host do banco de dados MySQL. Neste caso, o nome do host do banco de dados é `db`.
* `WORDPRESS_DB_USER`: O nome de usuário do banco de dados MySQL. Neste caso, o nome de usuário do banco de dados é `wpuser`.
* `WORDPRESS_DB_PASSWORD`: A senha do banco de dados MySQL. Neste caso, a senha do banco de dados é `wppass`.
* `WORDPRESS_DB_NAME`: O nome do banco de dados MySQL. Neste caso, o nome do banco de dados é `wpdb`.

**Volumes**

A configuração do Docker Compose também monta os seguintes volumes nos contêineres do WordPress e do banco de dados MySQL:

* `./wordpress:/var/www/html`: Este volume monta o diretório local `wordpress` no diretório `/var/www/html` do contêiner do WordPress. Isso permite que você edite os arquivos do seu site WordPress localmente e as alterações serão refletidas no contêiner do WordPress.
* `db:/var/lib/mysql`: Este volume monta o diretório local `db` no diretório `/var/lib/mysql` do contêiner do banco de dados MySQL. Isso permite que você persista os dados do seu banco de dados MySQL localmente.

**Redes**

A configuração do Docker Compose cria uma rede chamada `wpsite` e conecta todos os contêineres a esta rede. Isso permite que os contêineres se comuniquem entre si.

**PhpMyAdmin**

O contêiner do phpMyAdmin está configurado para se conectar ao banco de dados MySQL em execução no contêiner do banco de dados MySQL. Você pode acessar o phpMyAdmin em `http://localhost:8081`.

**Dicas**

* Se você precisar alterar as variáveis de ambiente ou volumes montados nos contêineres, você pode editar o arquivo `docker-compose.yml`.
* Se você precisar adicionar novos plugins ou temas ao seu site WordPress, você pode copiar os arquivos para o diretório `./wordpress`.
* Se você precisar fazer backup do seu banco de dados MySQL, você pode copiar o conteúdo do diretório `db` para um local seguro.

**Conclusão**

Esta configuração de Docker Compose fornece uma maneira fácil de implantar e gerenciar um site WordPress completo. Você pode usar esta configuração como base para criar o seu próprio site WordPress ou para contribuir com projetos da comunidade WordPress.
