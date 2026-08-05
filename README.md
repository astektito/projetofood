# Projeto Food

Backend en Laravel para un sistema de pedidos de comida (estilo restaurante / entrega a domicilio), desarrollado como proyecto academico para una asignatura de Desarrollo de Aplicaciones Distribuidas (IPL DAD).

## Tecnologias

- PHP 7.3+ / 8.0
- Laravel 8
- MySQL (configurable en `.env`)
- Laravel Mix (Webpack) para compilar los assets
- Composer y npm para gestionar dependencias

## Modelo de datos

Definido mediante migraciones y datos de ejemplo (seeders):

- **users**: usuarios con rol (`C` cliente, `EC` cocinero, `ED` repartidor, `EM` gerente).
- **customers**: datos del cliente (direccion, telefono, NIF).
- **products**: platos y bebidas (`hot dish`, `cold dish`, `drink`, `dessert`).
- **orders** y **order_items**: pedidos con estados (Holding, Preparing, Ready, in Transit, Delivered, Cancelled).

Los seeders cargan productos de ejemplo (cocina portuguesa) e imagenes desde `database/seeders`.

## Como ejecutar

```bash
composer install
npm install
cp .env.example .env      # configura la conexion a la base de datos
php artisan key:generate
php artisan migrate
php artisan db:seed        # carga datos de ejemplo
php artisan serve
```

## Estructura

- `app/` codigo de la aplicacion (modelos, middleware, providers).
- `database/migrations` esquema de la base de datos.
- `database/seeders` datos e imagenes de ejemplo.
- `routes/` rutas web y API.
- `config/` configuracion de Laravel.

> Nota: el proyecto parte del scaffold estandar de Laravel; el trabajo propio se centra en el modelo de datos y los seeders.

Autor: Edwin Astudillo
