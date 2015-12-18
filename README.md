Chargify Wrapper for Laravel 5 
=====================================

Updated to use 0.0.5 Chargify SDK.

This is a wrapper using the chargley chargify SDK. It creates a service provider and facade for autoloading into laravel.

How to Install
---------------

### Laravel 5.0

1.  Install the `brynnb/chargify-laravel` package. Before this works, you also need to add this repository to your composer.json file (since this isn't a registered package).

    ```shell
    $ composer require brynnb/chargify-laravel
    ```

1. Update `config/app.php` to activate ChargifyLaravel

    ```php
    # Add `ChargifyLaravelServiceProvider` to the `providers` array
    'providers' => array(
        ...
        brynnb\ChargifyLaravel\ChargifyLaravelServiceProvider::class,
    )

    # Add the `ChargifyLaravelFacade` to the `aliases` array
    'aliases' => array(
        ...
        'Chargify' => brynnb\ChargifyV2Laravel\ChargifyLaravelFacade::class
    )
    ```

1.  Generate a template Chargify config file

    ```shell
    $ php artisan vendor:publish
    ```

1.  Update your `/.env` file to have the parameters specified in `app/config/chargify.php`:

    ```php
    return array(
			'hostname' => env('CHARGIFY_HOSTNAME'),
			'api_key' => env('CHARGIFY_KEY'),
			'shared_key' => env('CHARGIFY_SHARED_KEY'),
			'api_id' => env('CHARGIFY_DIRECT_API_ID'),
			'api_password' => env('CHARGIFY_DIRECT_PASSWORD'),
			'api_secret' => env('CHARGIFY_DIRECT_SECRET'),
    );
    ```