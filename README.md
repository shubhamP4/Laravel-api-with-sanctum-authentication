--Laravel Version: 8.x
### Installation Via Composer
- **[Install](https://laravel.com/docs/9.x#installation-via-composer)**

## Laravel Sanctum
Laravel Sanctum provides a featherweight authentication system for SPAs (single page applications), mobile applications, and simple, token based APIs. Sanctum allows each user of your application to generate multiple API tokens for their account. These tokens may be granted abilities / scopes which specify which actions the tokens are allowed to perform.
## Installation

- **[composer require laravel/sanctum]()**

**************************************************
---> Next, you should publish the Sanctum configuration and migration files using the vendor:publish Artisan command. The sanctum configuration file will be placed in your application's config directory:

- **[php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"]()**


Finally, you should run your database migrations. Sanctum will create one database table in which to store API tokens:
- **[php artisan migrate]()**
**************************

##### Next, if you plan to utilize Sanctum to authenticate a SPA, you should add Sanctum's middleware to your api middleware group within your application's app/Http/Kernel.php file:
  
    \Laravel\Sanctum\Http\Middleware\EnsureFrontendRequestsAreStateful::class,
    'throttle:api',
    \Illuminate\Routing\Middleware\SubstituteBindings::class,],

**