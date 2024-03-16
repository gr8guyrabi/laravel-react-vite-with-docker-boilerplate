

use to spin up the container

1. docker compose up --build nginx -d #run required nginx server (main containers)
2. docker-compose run --rm composer require inertiajs/inertia-laravel #install inertiajs to run vite with laravel
3. docker compose run --rm artisan inertia:middleware
4. Head over to src/app/Http directory, then within Kernel.php file, add the following line in the $middlewareGroups[] array within its web[] array.

'web' => [
  // ...
  \App\Http\Middleware\HandleInertiaRequests::class,
],

5. For our routes to be recognized in the front end while rendering it with JavaScript instead of blade, we will use a special package called ziggy. Let’s install it using composer.

docker-compose run --rm composer require tightenco/ziggy

6. docker-compose run --rm laravel-migrate-seed

7. docker-compose up --build nginx -d

8. docker-compose run --rm composer install

9. docker-compose run --rm artisan key:generate
10. docker-compose run --rm artisan optimize