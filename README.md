# How to setup a simple docker container for laravel.

## Setup: 

1. Clone latest Laravel release from their repo: [https://github.com/laravel/laravel.git](https://github.com/laravel/laravel.git)

2. Install Composer via Docker 
	`docker run --rm -v $(pwd):/app composer/composer:php7 install`

3. Clone/Copy all files from the docker-laravel repo to the directory of your choosing.

4. Run Docker with the command:
	* `docker-compose up --build `
	* `docker-compose up --build -d` (for kitematic users)

5. In your laravel root Remember to rename .env-example to .env

6. Setting Laravel's Application key and Optimization, to run these commands we type
	* `docker-compose exec app php artisan key:generate`
	* `docker-compose exec app php artisan optimize`

6. To access it in your browser go to http://localhost:8080 

7. Start building in laravel :)


## Notes:

### Artisan: 

So to access Laravel's Artisan via Docker is pretty long winded you have to type:

`docker-compose exec app php artisan ....`

I recommnend adding an alias in your terminal's .bash_profile or ohmyzsh's .zshrc like so:

`alias docker-laravel="docker-compose exec app php artisan"`

This saves you a few key strokes here and there. Therefore to run an artisan command would be like so: 

`docker-laravel make:controller MyController`

### SQL Access
For DB access via Sequal Pro or similar remember to use port 33061 when you connect!






##### References
https://medium.com/@shakyShane/laravel-docker-part-1-setup-for-development-e3daaefaf3c


