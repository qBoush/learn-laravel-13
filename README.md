## Установка Laravel (пустой проект)

Обновление пакетного менеджера Composer до последней стабильной версии.

```bash
composer self-update
```

Скачивание и установка чистого каркаса Laravel в текущую директорию

```bash
composer create-project laravel/laravel .
```

Настройка приложения для работы в качестве API, установка Laravel Sanctum для аутентификации

```bash
php artisan install:api
```

Публикация файла конфигурации для настройки CORS-политики (разрешение cross-origin запросов к вашему API с других доменов/фронтенда).

```bash
php artisan config:publish cors
```

Создание символической ссылки из публичной папки **public/storage** в закрытую папку **storage/app/public**.
Это необходимо, чтобы загруженные файлы были доступны по прямой ссылке из браузера.

```bash
php artisan storage:link
```

Создание файла **.htaccess** в корне проекта, чтобы перенаправить все запросы в папку **public**.

```php
// Включает модуль mod_rewrite в веб-сервере Apache
RewriteEngine on
// Правило, которое берёт абсолютно любой запрошенный URL и незаметно для пользователя перенаправляет его в папку public/
RewriteRule ^(.*)$ public/$1 [L]
```

## Установка Laravel из репозитория


выполните клонирование репозитория в домашнюю директорию сайтов и установите все зависимости.

```bash
git clone https://github.com/qBoush/learn-laravel-13.git
composer install
```
Скопируем файл .env из файла **.env.example**

```bash
copy .env.example .env
```

Сгенерируем ключ шифрования 

```bash
php artisan key:generate
```

Выполните миграцию

```bash
php artisan migrate --seed
```

## Настройка подключения к БД

Настройте параметры подключения к БД (файл **.env**)

```php
DB_CONNECTION=mysql
DB_HOST=127.0.0.1 MySQL-8.4
DB_PORT=3306
DB_DATABASE=learn-laravel-13
DB_USERNAME=root
DB_PASSWORD=

SESSION_DRIVER=file
```
