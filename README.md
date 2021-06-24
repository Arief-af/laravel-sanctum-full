laravel new namaProject
Setting ENV

Install Fortify
-----------------------------------
composer require laravel/fortify
php artisan vendor:publish --provider="Laravel\Fortify\FortifyServiceProvider"

php artisan migrate

Add App\Providers\FortifyServiceProvider::class to config/app.php

Disable views in config/fortify.php

------------------------------------

Install Sanctum
composer require laravel/sanctum
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"

add \Laravel\Sanctum\Http\Middleware\EnsureFrontendRequestsAreStateful::class,
to API app/http/kernel.php

add HasApiTokens to user models ( optional )

---------------------------------------------

Setting cors on config/cors.php
Add 'api/*', 
        'login',
        'logout',
        'register',
        'forgot-password',
        'reset-password',
to paths
setting cors .env
ADD :
SANCTUM_STATEFUL_DOMAINS=localhost:8080
SESSION_DOMAIN=localhost

edit route to sanctum 'auth:sanctum

