Chargify Wrapper for Laravel 5 
=====================================

Updated to use 0.1.0 Chargify SDK that uses updated Guzzle. 

This is a wrapper using the chargley chargify SDK. It creates a service provider and facade for autoloading into laravel.

How to Install
---------------

### Laravel 5.0

1.  Install the `brynnb/chargify-laravel` package. Before this works, you also need to add this repository to your composer.json file (since this isn't a registered package).
	```shell
	"repositories": [
		{
		    "type": "vcs",
		    "url": "https://github.com/brynnb/chargify-laravel"
		}
	
	]
	```
then `composer require brynnb/chargify-laravel`
	

2. Update `config/app.php` to activate ChargifyLaravel

    ```php
    # Add `ChargifyLaravelServiceProvider` to the `providers` array
    'providers' => array(
        ...
        brynnb\ChargifyLaravel\ChargifyLaravelServiceProvider::class,
    )

    # Add the `ChargifyLaravelFacade` to the `aliases` array
    'aliases' => array(
        ...
        'Chargify' => brynnb\ChargifyLaravel\ChargifyLaravelFacade::class
    )
    ```

3.  Generate a template Chargify config file

    ```shell
    $ php artisan vendor:publish
    ```

4.  Update your `/.env` file to have the parameters specified in `app/config/chargify.php`:

    ```php
    return array(
			'hostname' => env('CHARGIFY_HOSTNAME'),
			'api_key' => env('CHARGIFY_KEY'),
			'shared_key' => env('CHARGIFY_SHARED_KEY')
    );
    ```
Credits
---------------
This is mostly the work of @andrewlamers, just modified to use the newer version of the SDK/Guzzle. Thanks Andrew!
