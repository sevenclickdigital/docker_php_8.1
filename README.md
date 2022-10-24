# localhost laravel TLS

Serviços de acesso `localhost:80` via `https://projeto.local` using `mkcert` and Nginx.

Adicionar `projeto.local` arquivo hosts:

```sh
sudo sh -c 'echo "127.0.0.1 projeto.local" >> /etc/hosts'
```

Configurar certificados com `mkcert`

```sh
# Install mkcert if needed
sudo apt install mkcert
mkcert -key-file certs/key.pem -cert-file certs/cert.pem projeto.local *.projeto.local
```

Subir os containers do projeto

```sh
docker-compose up -d --build
```

Acessar o container

Dando permissão ao arquivo

```sh
chmod +x ./bash.sh
```

```sh
./bash.sh
```

Instalar as dependências do projeto

```sh
composer install
```

Gerar a key do projeto Laravel

```sh
php artisan key:generate
```

# Acessando o projeto

Projeto
[https://projeto.local:81](https://projeto.local:81)

phpMyAdmin
[http://projeto:82](http://projeto:82)

E-mail - mailhog
[http://projeto:83](http://projeto:83)
