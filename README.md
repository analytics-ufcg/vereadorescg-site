# Nossos Vereadores

## Dependências
### Backend

R (>3.3):

```
# Necessário em máquinas ubuntu para instalar o R > 3.3
echo 'deb http://cran.rstudio.com/bin/linux/ubuntu trusty/' | sudo tee /etc/apt/sources.list.d/vereadores.list
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E084DAB9

sudo apt-get -y update
sudo apt-get -y install r-base

# necessários para alguns dos pacotes que instalaremos
sudo apt-get -y install libcurl4-openssl-dev
sudo apt-get -y install libpq-dev
```

Todos os pacotes de R serão instalados assim que você abrir a primeira sessão R (o 'packrat' vai cuidar de tudo :)

### Frontend

> bundle install

Servir via *RStudio*

> brocks::blog_serve()

Servir via *Linha de Comando*

> Rscript -e 'brocks::blog_serve()'

### Dados

É necessária a instalação do [PostgreSQL](https://www.postgresql.org/download/), com senha e usuário padrão. Com o *psql* aberto, crie um banco de dados chamado camara_db.

> CREATE DATABASE camara_db;

Os dados se encontram nesse repositório https://github.com/augustoqm/cg-insights-data. Baixe o [dump](https://github.com/augustoqm/cg-insights-data/blob/master/dump_camara_db_23-12-16.zip) mais recente e povoe o banco de dados criado.

> psql camara_db < camara_db_dump_23-12-16_since_1985.dump
