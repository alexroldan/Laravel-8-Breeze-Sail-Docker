# Laravel-8-Breeze-Sail-Docker
Documentation to develop Laravel 8 with Breeze in docker container

## Assumptions
Docker-desktop is already installed on Windows 10 machine. \
The WSL2 and Ubuntu are already installed.

Restart docker-desktop if it is running


# VIA WINDOWS TERMINAL

`c:\ wsl`

`$ cd ~`

`$ sudo curl -s https://laravel.build/example-app | bash`

> The files are located in \\\wsl$\ubuntu\home\example-app \
> open network in windows explorer and map the url

`$ cd example-app`

`$ ./vendor/bin/sail up -d`

`$ nano ~/.bashrc `

> At the bottom of the file add ->  `alias sail='bash vendor/bin/sail'`

`$ . ~/.bashrc`

`$ sail down`

`$ sail up -d/`

`$ sail artisan migrate`

`$ code .`

> Install remote-wsl then close vscode

`$ code .`


# BREEZE

`$ sail composer require laravel/breeze --dev`

`$ sail artisan breeze:install vue`

`$ sail npm install`

`$ sail artisan migrate`

`$ sail npm ci`
`
$ sail npm run dev`

`$ code .`

`$ sail npm run watch-poll`


# STARTING DOCKER THE NEXT DAY

`c:\ wsl`

`$ cd ~ && cd example-app && sail up -d && code .`

`$ sail npm run watch-poll`

`$ sail down`



# BROWSER SYNC

`$ sail npm install browser-sync browser-sync-webpack-plugin@^2.3.0 --save-dev --legacy-peer-deps`

`$ sail npx mix`

	npx mix watch
	
	npx mix watch -- --watch-options-poll=1000
	
	npx mix watch --hot //not working
	

`docker-compose.yml`

	ports:
	
		- '${APP_PORT:-80}:80'
		
		- 3000:3000
		
		- 3001:3001
		

`$ sail down`

`$ sail build --no-cache`

`$ sail up -d`

`$ sail npm run watch-poll`




# HELPER COMMANDS

`$ sail artisan config:cache && sail artisan route:cache && sail artisan optimize`

`$ sail artisan config:clear && sail artisan route:clear`

> open-source database management tool \
> https://www.heidisql.com/download.php



# php.validate.executablePath error in vscode

`sudo touch /usr/local/bin/php`

`sudo chmod +x /usr/local/bin/php`

`sudo nano /usr/local/bin/php`

> Write out the commands

	path=$(printf '%s\n' "${PWD##*/}")
	command="docker exec ${path}_laravel.test_1 php "$@""
	echo "Running php on docker ${path}_laravel.test_1"
	$command
-----------------------------------------------------



