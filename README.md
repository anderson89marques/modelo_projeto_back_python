# Sugestão de estrutura para os projetos SME-AMCOM python 

Organização de um projeto python AMcom-SME.

Versão: 0.0.1

### Para desenvolver

I)  Clone o repositório.
```console
$ git clone https://github.com/anderson89marques/modelo_projeto_back_python.git back
$ cd back
```

II)  Crie um Virtualenv com Python 3.6
```console
$ python -m venv .venv
```

III.  Ative o Virtualenv.
```console
$ source .venv/bin/activate
```

IV.  Instale as dependências.
```console
$ pip install -r requirements\local.txt
```

V.  Configure a instância com o .env
```console
$ cp env_sample .env
```

VI. Link o clone com o repositório do seu projeto
```
$ git remote add origin <link do seu repositório>
```

## Executando com docker 

- Clone o repositório
```console
$ git clone https://github.com/anderson89marques/modelo_projeto_back_python.git back
```

- Entre no diretório criado
```console
$ cd back
```

- cp env_sample .env
```console
cp env-sample
```

- Execute o docker
```console
$ docker-compose up --build -d
```

- Crie um super usuário no container criado
```console
$ docker-compose run --rm django sh -c "python manage.py createsuperuser"
```

- Acesse a url para verificar a versão (Faça o login primeiro com o usuário criado).
```console
http://localhost:8000/api/versao
```

### Filas Celery
**Subir o Celery Worker**
```console
$ celery  -A config worker --loglevel=info
```

**Subir o Celery Beat**
```console
$ celery  -A config beat --loglevel=info
```

**Limpar os processos no celery**
```console
$ celery  -A config purge
```