![wordpress-docker](https://github.com/andrepfdev/wordpress-docker/assets/49399742/8f25e1f7-650e-44de-91f8-9d11f854899c)

## WordPress & Docker

**README.md**

**WordPress, MariaDB e phpMyAdmin com Docker Compose**

Este repositório contém um arquivo docker-compose.yml para iniciar um ambiente WordPress completo, incluindo MariaDB e phpMyAdmin.

**Pré-requisitos**

* Docker
* Docker Compose

**Como usar**

1. Clone este repositório:

```
git clone https://github.com/andrepfdev/wordpress-docker.git
```

2. Acesse o diretório do repositório:

```
cd wordpress-docker
```

3. Crie a rede do Docker:

```
docker-compose up -d network
```

4. Crie os contêineres do WordPress, MariaDB e phpMyAdmin:

```
docker-compose up -d
```

5. Aguarde alguns segundos para que os contêineres sejam iniciados.

**Acesse o WordPress**

O WordPress estará disponível na porta 8080 do seu navegador:

```
http://localhost:8080
```

**Acesse o phpMyAdmin**

O phpMyAdmin estará disponível na porta 8081 do seu navegador:

```
http://localhost:8081
```

**Credenciais**

* Banco de dados:
    * Nome do banco de dados: wpdb
    * Usuário do banco de dados: wpuser
    * Senha do banco de dados: wppass

* phpMyAdmin:
    * Senha do usuário root: root

**Volumes**

Os volumes do Docker são usados para persistentes os dados dos seus contêineres. Os seguintes volumes são usados neste arquivo docker-compose.yml:

* **db:** Este volume armazena os dados do banco de dados MariaDB.
* **wordpress:** Este volume armazena os arquivos do WordPress.

Você pode modificar o conteúdo dos volumes copiando arquivos para os diretórios correspondentes no diretório do repositório. Por exemplo, para copiar os arquivos do seu tema WordPress para o volume wordpress, você pode executar o seguinte comando:

```
cp -r meu_tema /wordpress-docker-compose/wordpress/wp-content/themes/
```

**Dicas**

* Você pode usar a variável de ambiente `PMA_ARBITRARY` para habilitar o acesso ao phpMyAdmin de fora da rede do Docker. Para fazer isso, defina a variável de ambiente como `1` no arquivo docker-compose.yml.
* Você pode usar o comando `docker-compose logs` para visualizar os logs dos seus contêineres.
* Você pode usar o comando `docker-compose down` para parar e remover os seus contêineres.

**Licença**

Este repositório é licenciado sob a licença MIT.
