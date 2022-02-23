# Prueba Laravel 9 - Mongo DB
+ Repositorio GitHub: https://github.com/petrix12/fid_2022.git

## Antes de iniciar:
1. Crear proyecto en la página de [GitHub](https://github.com) con el nombre: **prueba-laravel-monogo-2022**.
    + **Description**: Proyecto de Laravel 9 con MongoDB para realizar pruebas.
    + **Private**.
2. En la ubicación raíz del proyecto en la terminal de la máquina local:
    + $ git init
    + $ git add .
    + $ git commit -m "Antes de iniciar"
    + $ git branch -M main
    + $ git remote add origin https://github.com/petrix12/prueba-laravel-monogo-2022.git
    + $ git push -u origin main


## Preparar el entorno de desarrollo

### Instalar MongoDB en Windows con Laragon
+ https://www.mongodb.com/es
+ https://laragon.org/docs/quick-add.html
+ https://forum.laragon.org/topic/815/mongodb-addon-for-laragon
1. Ejecutar **Laragon** e ir a **Menú > Herramientas > Quick add > mongodb-4** para instalar MongoDB.
    + **Nota**: MongoDB se instalará en **C:\laragon\bin\mongodb\mongodb-4.0.3**
    + **Ruta para ejecutar MongoDB**: C:\laragon\bin\mongodb\mongodb-4.0.3\
2. Reiniciar los servicios de **Laragon** para activar los servicios de **MongoDB**.


### Agregar la extensión (DLL) de MongoDB a PHP en Windows/Laragon
+ https://forum.laragon.org/login
1. Ir a https://www.mongodb.com/try/download/community
2. Descargar en formato **zip** la versión actual de MongoDB para tu SO.
3. Descomprimir la descarga y extraer la carpeta **bin** (lo demás se puede eliminar).
4. Renombrar la carpeta **bin** a **mongodb-[versión]** (Ejm.: **mongodb-5.03**) y ubicarla en:
    + C:\laragon\bin\mongodb
5. En laragon ir a **Menú > MongoDB** y cambiar la versión a la nueva.
6. Anexar la siguiente ruta a las variables de entorno de Windows:
    + C:\laragon\bin\mongodb\mongodb-[versión]
7. Ir a https://pecl.php.net/package/mongodb y descargar la DLL (**X:X Thread Safe (TS) x64**) de la versión más actual y estable.
8. Descomprimimos la descargas y movemos el archivo **php_mongodb.dll** a **C:\laragon\bin\php\php-7.4.19-Win32-vc15-x64\ext** el resto de la descarga lo borramos.
9.  Modificar el archivo de configuración **C:\laragon\bin\php\php-7.4.19-Win32-vc15-x64\php.ini** para agregar la extensión de MongoDB **extension=php_mongodb.dll**:
    ```ini
    ≡
    ;extension=soap
    ;extension=sockets
    ;extension=sodium
    ;extension=sqlite3
    ;extension=tidy
    ;extension=xmlrpc
    extension=xsl
    extension=php_mongodb.dll

    ;;;;;;;;;;;;;;;;;;;
    ; Module Settings ;
    ;;;;;;;;;;;;;;;;;;;
    ≡
    ```
    + **Nota**: de aquí en adelante se podrá usar la nueva versión de MongoDB en cualquier proyecto de PHP en Laragon.


## Conectar MongoDB con PHP utilizando XAMPP y Composer:
1. Ir a https://www.mongodb.com/try/download/community
2. Descargar e instalar la versión actual de MongoDB para tu SO.
3. Iniciar los servicios de MongoDB ejecutano en una terminal:
    + mongod
4. Anexar la siguiente ruta a las variables de entorno de Windows:
    + C:\Program Files\MongoDB\Server\5.0\bin
5. Ir a https://pecl.php.net/package/mongodb y descargar la DLL (**X:X Thread Safe (TS) x64**) de la versión más actual y estable.
6. Descomprimimos la descargas y movemos el archivo **php_mongodb.dll** a **C:\xampp\php\ext** el resto de la descarga lo borramos.
7. Modificar el archivo de configuración **C:\xampp\php\php.ini** para agregar la extensión de MongoDB **extension=php_mongodb.dll**:
    ```ini
    ≡
    ;extension=soap
    ;extension=sockets
    ;extension=sodium
    ;extension=sqlite3
    ;extension=tidy
    ;extension=xmlrpc
    ;extension=xsl
    extension=php_mongodb.dll

    ;;;;;;;;;;;;;;;;;;;
    ; Module Settings ;
    ;;;;;;;;;;;;;;;;;;;
    ≡
    ```
8. Para probar la correcta instalación:
    + Crear archivo **C:\xampp\htdocs\test.php**:
        ```php
        <?php
            echo phpinfo();
        ?>
        ```
    + En un navegador escribimos la siguiente ruta:
        + http://localhost/test.php
            + **Nota**: verificar que este encendido el servidor **Apache** de **XAMPP**.
        + **Nota**: si todo salio bien debe aparecer el servicio de mongodb en la página.
9. Ir a https://getcomposer.org y descargar e instalar Composer.
    + **Nota**: verificar que la ruta completa de PHP sea:
        + C:\xampp\php\php.exe
10. Ejeuctar la siguiente instrucción para todos aquellos proyectos que requieran de MongoDB:
    + $ composer require mongodb/mongodb

## Conectar MongoDB con PHP utilizando Laragon y Composer:
1. Ir a https://www.mongodb.com/try/download/community
2. Descargar en formato **zip** la versión actual de MongoDB para tu SO.
3. Descomprimir la descarga y extraer la carpeta **bin** (lo demás se puede eliminar).
4. Renombrar la carpeta **bin** a **mongodb-[versión]** (Ejm.: **mongodb-5.03**) y ubicarla en:
    + C:\laragon\bin\mongodb
5. En laragon ir a **Menú > MongoDB** y cambiar la versión a la nueva.
5. Anexar la siguiente ruta a las variables de entorno de Windows:
    + C:\laragon\bin\mongodb\mongodb-[versión]
6. Ir a https://pecl.php.net/package/mongodb y descargar la DLL (**X:X Thread Safe (TS) x64**) de la versión más actual y estable.
7. Descomprimimos la descargas y movemos el archivo **php_mongodb.dll** a **C:\laragon\bin\php\php-7.4.19-Win32-vc15-x64\ext** el resto de la descarga lo borramos.
8. Modificar el archivo de configuración **C:\laragon\bin\php\php-7.4.19-Win32-vc15-x64\php.ini** para agregar la extensión de MongoDB **extension=php_mongodb.dll**:
    ```ini
    ≡
    ;extension=soap
    ;extension=sockets
    ;extension=sodium
    ;extension=sqlite3
    ;extension=tidy
    ;extension=xmlrpc
    extension=xsl
    extension=php_mongodb.dll

    ;;;;;;;;;;;;;;;;;;;
    ; Module Settings ;
    ;;;;;;;;;;;;;;;;;;;
    ≡
    ```
9.  Para probar la correcta instalación:
    + Crear archivo **C:\laragon\www\test\test.php**:
        ```php
        <?php
            echo phpinfo();
        ?>
        ```
    + En un navegador escribimos la siguiente ruta:
        + http://test.test
            + **Nota**: verificar que esten levantados los servicios de **Laragon**.
        + **Nota**: si todo salio bien debe aparecer el servicio de mongodb en la página.
10. Ir a https://getcomposer.org y descargar e instalar Composer.
    + **Nota**: verificar que la ruta completa de PHP sea:
        + C:\laragon\bin\php\php-7.4.19-Win32-vc15-x64\php.exe
11. Ejeuctar la siguiente instrucción para todos aquellos proyectos que requieran de MongoDB:
    + $ composer require mongodb/mongodb


## Crear proyecto e instalar dependencias para MongoDB
+ https://github.com/jenssegers/laravel-mongodb
1. Ejecutar:
    + $ composer create-project laravel/laravel fid "9.*"
    + $ composer require mongodb/mongodb
    + $ composer require jenssegers/mongodb


## Configurar la base de datos
1. Agregar los parámetros de configuración de MongoDB en el archivo de configuración **config\database.php**:
    ```php
    ≡
    return [
        ≡
        'connections' => [

            'mongodb' => [
                'driver' => 'mongodb',
                'dsn'=> env('DB_DSN', ''),
                'host' => env('DB_HOST', '127.0.0.1'),
                'port' => env('DB_PORT', 27017),
                'database' => env('DB_DATABASE', 'laramongo'),
                'username' => env('DB_USERNAME', ''),
                'password' => env('DB_PASSWORD', ''),
                'options' => [
                    // here you can pass more settings to the Mongo Driver Manager
                    // see https://www.php.net/manual/en/mongodb-driver-manager.construct.php under "Uri Options" for a list of complete parameters that you can use
            
                    'database' => env('DB_AUTHENTICATION_DATABASE', 'admin'), // required with Mongo 3+
                ],
            ],

            'sqlite' => [
                ≡
            ],
            ≡
        ],
        ≡
    ];
    ```
2. Configurar las variables de entorno de baso de datos del archivo **.env** para establecer MongoDB como base de datos:
    ```php
    DB_CONNECTION=mongodb
    DB_HOST=127.0.0.1
    DB_PORT=27017
    DB_DATABASE=laramongo
    DB_USERNAME=
    DB_PASSWORD=
    ```
    + **Nota**: La base de datos de MongoDB se creará sola cuando se ejecute la primera inserción en ella, por tal motivo no tendremos que crearla previamente.

## Crear sistema de autenticación
1. Ejecutar:
    + $ composer require laravel/ui
    + $ php artisan ui bootstrap --auth
    + $ npm install
    + $ npm run dev


### Adaptar el modelo User a MongoDB
1. Modificar el modelo **app\Models\User.php** para realizar adaptaciones con MongoDB:
    ```php
    <?php

    namespace App\Models;

    ≡
    /* use Illuminate\Foundation\Auth\User as Authenticatable; */
    use Jenssegers\Mongodb\Auth\User as Authenticatable;
    ≡
    ```



+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++






## Comandos Git:
+ Historial de commit:
    + git log --pretty=oneline
+ Borrar ultimo commit:
    + git reset HEAD^ --soft
+ Forzar push
    + git push origin -f





---------------------------------------------------------------------
## Creación del proyecto Laravel - Jetstream
1. Crear proyecto **fid_2022**:
    + $ laravel new fid_2022 --jet
    + Seleccionar **livewire**.
    + No trabajaremos con equipos:
        - Will your application use teams? (yes/no) [no]: no
2. Instalar Node Package Manager y compilar sus dependencias:
    + $ npm install
    + $ npm run dev
3. Crear un dominio local: **fid_2022.test**.
    + [Guía de Coders Free para crear un dominio local](https://codersfree.com/blog/como-generar-un-dominio-local-en-windows-xampp)
4. Crear base de datos **fid_2022** en MySQL (Cotejamiento: **utf8_general_ci**).
5. Hacer coincidir los parámetros de base de datos y de dominio del proyecto en **.env** en caso de ser necesario:
    ```env
    APP_NAME="FID"
    ≡
    APP_URL=http://fid_2022.test
    ≡
    DB_DATABASE=fid_2022
    ≡
    ```
6. Ejecutar migraciones:
    + $ php artisan migrate
7. Realizar commit:
    + $ git add .
    + $ git commit -m "Creación del proyecto Laravel - Jetstream"
    + $ git push -u origin main

## Creación del esqueleto del proyecto
1. Modificar vista **resources\views\welcome.blade.php** para adaptarla al proyecto **FID** como página de **bienvenida**.
2. Modificar vista **resources\views\dashboard.blade.php** para adaptarla al proyecto **FID** como página de **inicio**.
3. Modificar menú de navegación **resources\views\navigation-menu.blade.php**.
4. Crear archivo de rutas **routes\admin.php** para administrar el módulo de administración (**admin**):
    ```php
    <?php

    use Illuminate\Support\Facades\Route;
    ```
5. Crear archivo de rutas **routes\formation.php** para administrar el módulo de formación (**formation**):
    ```php
    <?php

    use Illuminate\Support\Facades\Route;
    ``` 
6. Crear archivo de rutas **routes\investigation.php** para administrar el módulo de formación (**investigation**):
    ```php
    <?php

    use Illuminate\Support\Facades\Route;
    ``` 
7. Crear archivo de rutas **routes\documentation.php** para administrar el módulo de documentación (**documentation**):
    ```php
    <?php

    use Illuminate\Support\Facades\Route;
    ``` 
8. Crear archivo de rutas **routes\diffusion.php** para administrar el módulo de difusión (**diffusion**):
    ```php
    <?php

    use Illuminate\Support\Facades\Route;
    ```
9. Registrar los nuevos archivos de rutas en el provider **app\Providers\RouteServiceProvider.php**:
    ```php
    ≡
    public function boot()
    {
        $this->configureRateLimiting();

        $this->routes(function () {
            Route::prefix('api')
                ->middleware('api')
                ->namespace($this->namespace)
                ->group(base_path('routes/api.php'));

            Route::middleware('web')
                ->namespace($this->namespace)
                ->group(base_path('routes/web.php'));

            Route::middleware('web', 'auth')
                ->name('admin.')
                ->prefix('admin')
                ->namespace($this->namespace)
                ->group(base_path('routes/admin.php'));
                
            Route::middleware('web')
                ->name('formation.')
                ->prefix('formation')
                ->namespace($this->namespace)
                ->group(base_path('routes/formation.php'));
                
            Route::middleware('web')
                ->name('investigation.')
                ->prefix('investigation')
                ->namespace($this->namespace)
                ->group(base_path('routes/investigation.php'));
                
            Route::middleware('web')
                ->name('documentation.')
                ->prefix('documentation')
                ->namespace($this->namespace)
                ->group(base_path('routes/documentation.php'));
                
            Route::middleware('web')
                ->name('diffusion.')
                ->prefix('diffusion')
                ->namespace($this->namespace)
                ->group(base_path('routes/diffusion.php'));
        });
    }
    ≡
    ```
10. Estructura los directorios del proyecto para las **vistas**:
    + resources\views\admin
    + resources\views\formation
    + resources\views\investigation
    + resources\views\documentation
    + resources\views\diffusion
11. Estructura los directorios del proyecto para los **modelos**:
    + app\Models\admin
    + app\Models\formation
    + app\Models\investigation
    + app\Models\documentation
    + app\Models\diffusion
12. Estructura los directorios del proyecto para los **controladores**:
    + app\Http\Controllers\admin
    + app\Http\Controllers\formation
    + app\Http\Controllers\investigation
    + app\Http\Controllers\documentation
    + app\Http\Controllers\diffusion
13. Realizar commit:
    + $ git add .
    + $ git commit -m "Creación del esqueleto del proyecto"
    + $ git push -u origin main

## Instalación de dependencias principales
+ [Laravel Permission](https://spatie.be/docs/laravel-permission/v3/basic-usage/basic-usage)
+ [Laravel AdminLTE](https://github.com/jeroennoten/Laravel-AdminLTE)
+ [Plantilla AdminLTE](https://adminlte.io/themes/v3/index.html)
+ [Documentación Laravel Collective](https://laravelcollective.com/docs/6.x/html)
+ [Sweetalert2](https://sweetalert2.github.io)
+ [Bootstrap GitHub](https://github.com/twbs/bootstrap)
+ [Bootstrap npm](https://www.npmjs.com/package/bootstrap)
1. Instalación de **Laravel Permission** para la implementación de un sistema de roles y permisos:
    + $ composer require spatie/laravel-permission
    + Publicar las vistas de Laravel Permission:
        + $ php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"
    + Ejecutar las migraciones:
        + $ php artisan migrate
    + Implementar el trait **HasRoles** en el modelo **User**:
        ```php
        ≡
        use Spatie\Permission\Traits\HasRoles;

        class User extends Authenticatable
        {
            ≡
            use HasRoles;
            ≡
        }
        ```
2. Integración de plantilla **AdminLTE** para el panel administrativo:
	+ $ composer require jeroennoten/laravel-adminlte
    + $ php artisan adminlte:install
    + Publicar vista de AdminLTE:
        + $ php artisan adminlte:install --only=main_views
        + **Nota 1**: En **resources\views\vendor\adminlte\page.blade.php** es de donde se extienden las plantillas.
        + **Nota 2**: Modelo de uso de la plantilla AdminLTE:6. Diseñar vista para pruebas **resources\views\admin\index.blade.php**:
            ```php
            @extends('adminlte::page')

            @section('title', 'Sistemas de roles y permisos | Soluciones++')

            @section('content_header')
                <h1>Sistemas de roles y permisos</h1>
            @stop

            @section('content')
                <p>Sistemas de roles y permisos</p>
            @stop

            @section('css')
                {{-- ARCHIVOS CSS REQUERIDOS POR LA APLICACIÓN --}}
            @stop

            @section('js')
                {{-- ARCHIVOS JS REQUERIDOS POR LA APLICACIÓN --}}
            @stop
            ```
3. Instalar **Laravel Collective** para hacer formularios:
    + $ composer require laravelcollective/html
4. Instalar **Sweetalert2** para notificaciones:
    + $ php artisan adminlte:plugins install
    + Modificar en **config\adminlte.php**:
        ```php
        ≡
        'Sweetalert2' => [
            'active' => true,   /* Activamos para todas las vistas de la plantilla Sweetalert2 */
            'files' => [
                [
                    'type' 		=> 'js',
                    'asset' 	=> true,
                    'location' 	=> 'vendor/sweetalert2/sweetalert2.all.min.js',
                ],
            ],
        ],
        ≡
        ```
    + Agregamos la siguiente instrucción al archivo **resources\js\app.js**:
        ```js
        window.Swal = require('sweetalert2');
        ```
    + $ npm install sweetalert2
	+ $ npm run dev
5. Instalar Bootstrap:
    + $ npm install bootstrap
7. Instalar Font Awesome:
    + $ npm i font-awesome
8. Realizar commit:
    + $ git add .
    + $ git commit -m "Instalación de dependencias principales"
    + $ git push -u origin main

## Configurar un servicio de base de datos MongoDB

## Crear un servicio de base de datos MySQL en AWS

## Crear un servicio de base de datos MongoDB en AWS

## Deploy del proyecto en AWS

    ```php
    ```

## Comandos Git
+ Crear repositorio local:
    + $ git init
+ Agregar cambios al staging:
    + $ git add .
+ Realizar confirmación de los cambios (empaquetar los cambios):
    + $ git commit -m "Antes de iniciar"
+ Crear rama principal
    + $ git branch -M main
+ Enlazar repositorio Local con proyecto GitHub
    + $ git remote add origin https://github.com/petrix12/fid_2022.git
+ Sincronizar de Local a GitHub:
    + $ git push -u origin main


+ Sincronizar de GitHub a Local:
    + $ git pull --rebase origin



+ Configuración de email:
    + $ git config --global user.email "bazo.pedro@gmail.com"
+ Configuración del nombre de usuario:
    + $ git config --global user.name "Pedro Bazó"
+ Verificar los datos guardados de configuración:
    + $ git config --global -e  (muestra el resultado en el editor de texto predeterminado)
    + $ git config --global -l  (muestra el resultado en la misma terminal)
    + $ git config user.name    (muestra el nombre de usuario)
    + $ git config user.email   (muestra el eamil de usuario)
+ Listar la configuración inicial de Git:
    + $ git config --list
+ Verificar modificaciones en repositorio:
    + $ git status
+ Sacar un archivo del staging:
    + $ git reset HEAD archivo.txt
+ Regresar todo al commit anterior (se perderán todos los cambios): 
    + $ git checkout .
+ Ver todos los commits:
    + $ git log
    + $ git show
+ Volver a un commit determinado:
    + $ git checkout 0e26441c67500daa2b3cc16a101f8994e57c6dff
+ Crear una rama:
    + $ git branch nueva_rama
+ Ver en que rama estamos:
    + $ git branch
+ Cambiar de rama:
    + $ git branch otra_rama
+ Unir una rama con la principal:
    + $ git merge rama_a_unir
+ Eliminar una rama:
    + $ git branch -d rama_a_eliminar
+ Traer las actualizaciones desde GitHub:
    + git pull origin main



## Deploy en DigitalOcean
+ https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04-es
+ https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-20-04

### Creación del cloud
1. Ingresar a [DigitalOcean](https://cloud.digitalocean.com/login).
2. Crear Droplets (Create cloud servers).
3. Seleccionar un sistema operativo Ubuntu y seleccione:
    + Select additional options:
        + Monitoring
        + IPv6
        + User data
    + Choose a hostname: fid-2022

### Conexión SSH con PuTTY en windows
+ https://docs.digitalocean.com/products/droplets/how-to/connect-with-ssh/putty
1. Descargar e instalar PuTTY en https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html
2. Ejecutar y configurar PuTTY:
    + Session:
        + Nombre de host (o dirección IP): ************
        + Port: 22
        + Tipo de conexión: SSH
    + Connection
        + Data:
            + Nombre de usuario de inicio de sesión automático: root
        + SSH: Asegúrese de que **2** esté seleccionado para la versión del protocolo SSH.
    + Session:
        + Sesiones guardadas: **fid2022**
        + Presionar el botón **Save**
3. Conexión SSH:
    + Ejecutar PuTTY:
    + Session:
        + Seleccionar session: **fid2022**
        + Presionar botón **Load**
        + Presionar botón **Open**
    + **Nota**: se abrirá una terminal solicitando la clave y listo.

### Configurar servidor web
1. En la terminal del servidor del proyecto **fid-2022** en DigitalOcean:
    + Actualizar servidor:
        + $ sudo apt-get update
        + $ sudo apt-get upgrade
        + Do you want to continue? [Y/n]: y
    + Actualizar nuevamente el servidor:
        + $ sudo apt-get update
    + Configurar entorno para ejecutar Laravel:
        + $ sudo apt-get install software-properties-common
        + $ sudo add-apt-repository ppa:ondrej/php
        + Press [ENTER] to continue or Ctrl-c to cancel adding it: ENTER.
    + Actualizar nuevamente el servidor:
        + $ sudo apt-get update
    + Instalar php:
        + $ sudo apt-get install php7.4
        + Do you want to continue? [Y/n]: y
    + Instalar el servidor apache:
        + $ sudo apt-get install apache2
        + $ sudo apt-get install libapache2-mod-php7.4
        + Para ver la versión de php:
            + $ php -v
        + Para saber los modulos instalados en php:
            + $ php -m
            + **Nota**: Constrastar contra **https://laravel.com/docs/8.x/deployment#server-requirements** y verificar cuales son necesarias.
    + Instalar extensiones de php necesarias para Laravel:
        + $ sudo apt-get install php7.4-bcmath
        + $ sudo apt-get install php7.4-mbstring
            + Do you want to continue? [Y/n]: y
        + $ sudo apt-get install php7.4-xml
    + Instalar paquetes que necesitaremos más adelante:
        + $ sudo apt-get install unzip
        + $ sudo apt-get install php7.4-zip
            + Do you want to continue? [Y/n]: y
        + $ sudo apt-get install php7.4-mysql
        + $ sudo apt-get install php7.4-curl
    + Reiniciar el servidor apache:
        + $ sudo service apache2 restart
    + Para verificar que no tengamos ningún error:
        + $ sudo service apache2 status
    + Habilitar el modulo rewrite
        + $ sudo a2enmod rewrite
    + Reiniciar el servidor apache:
        + $ sudo service apache2 restart
    + Definir punto de acceso a nuestra aplicación web:
        + Ingresar a la ruta: /var/www/html
            + $ cd /var/www/html
            + **Nota 1**: para ver los archivos contenidos en una ruta:
                + $ ls
            + **Nota 2**: para editar el archivo **index.html**:
                + $ sudo nano index.html
                + Para guardar, presionar:
                    + Ctrl + X
                    + y
                    + ENTER
    + Editar archivo de configuración de punto de acceso:
        + $ sudo nano /etc/apache2/sites-enabled/000-default.conf
            + Cambiar línea:
                * DocumentRoot /var/www/html
            + Por:
                * DocumentRoot /var/www/fid_2022/public
            + Para guardar, presionar:
                + Ctrl + X
                + y
                + ENTER
    + Reiniciar el servidor apache:
        + $ sudo service apache2 restart

### Instalar Composer en servidor web
1. Copiar de la página: **https://getcomposer.org/download**, el bloque de **Command-line installation**:
```
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === '906a84df04cea2aa72f40b5f787e49f22d4c2f19492ac310e8cba5b96ac8b64115ac402c8cd292b8a03482574915d1a8') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
```
2. En la terminal del servidor web pegar las líneas de comandos que acabamos de copiar y presionar ENTER.
3. Realizar la instalación global de composer:
    + $ sudo mv composer.phar /usr/local/bin/composer
    + **Nota**: Este comando se encuentra en **https://getcomposer.org/doc/00-intro.md**
    + Para comprobar que tenemos instalado composer, ejecutar:
        + $ composer

### Clonar nuestro repositorio de Git
1. Ir a la ruta **/var/www**:
    + $ cd /var/www
2. Clonar el repositorio del proyecto:
    + $ sudo git clone https://github.com/petrix12/fid_2022.git
3. Ir a la ruta **/var/www/awsejemplo**:
    + $ cd /var/www/fid_2022
4. Para poder instalar las dependencias de composer, ejecutar:
    + $ sudo chown -R root:www-data .
5. Ejecutar permisos para la carpeta de laravel:
    + $ chmod -R 755 .
    + $ chmod -R 777 ./storage
6. Instalar composer:
    + $ composer install
7. Crear el archivo **.env**:
    + $ touch /var/www/fid_2022/.env
8. Eidtar archivo de variable de entorno **.env**:
    + $ sudo nano /var/www/fid_2022/.env
        ```env
        APP_NAME=FID
        APP_ENV=production
        APP_KEY=base64:pe5xSWArGyI1gjwQVYV/vbbdEuyCh0O+ozbP3BJqjJs=
        APP_DEBUG=false
        APP_URL=http://137.184.246.143

        LOG_CHANNEL=stack
        LOG_DEPRECATIONS_CHANNEL=null
        LOG_LEVEL=debug

        DB_CONNECTION=mysql
        DB_HOST=107.180.2.195
        DB_PORT=3306
        DB_DATABASE=fid
        DB_USERNAME=pxvim6av41qx
        DB_PASSWORD="L5=Rj#8lW}YuK"

        BROADCAST_DRIVER=log
        CACHE_DRIVER=file
        FILESYSTEM_DRIVER=local
        QUEUE_CONNECTION=sync
        SESSION_DRIVER=database
        SESSION_LIFETIME=120

        MEMCACHED_HOST=127.0.0.1

        REDIS_HOST=127.0.0.1
        REDIS_PASSWORD=null
        REDIS_PORT=6379

        MAIL_MAILER=smtp
        MAIL_HOST=mailhog
        MAIL_PORT=1025
        MAIL_USERNAME=null
        MAIL_PASSWORD=null
        MAIL_ENCRYPTION=null
        MAIL_FROM_ADDRESS=null
        MAIL_FROM_NAME="${APP_NAME}"

        AWS_ACCESS_KEY_ID=
        AWS_SECRET_ACCESS_KEY=
        AWS_DEFAULT_REGION=us-east-1
        AWS_BUCKET=
        AWS_USE_PATH_STYLE_ENDPOINT=false

        PUSHER_APP_ID=
        PUSHER_APP_KEY=
        PUSHER_APP_SECRET=
        PUSHER_APP_CLUSTER=mt1

        MIX_PUSHER_APP_KEY="${PUSHER_APP_KEY}"
        MIX_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}"
        ```
9.  Generar llave del proyecto:
    + $ php artisan key:generate
10. Instalar NodeJs:
    + $ sudo apt install nodejs
        * Do you want to continue? [Y/n]: y
11. Para ver la versión de NodeJs:
    + $ nodejs -v
12. Actualizar NodeJs:
    + $ curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
13. Ejecutar:
    + $ sudo apt-get install -y nodejs
14. Para ver la versión de npm:
    + $ npm -v
15. Ejecutar:
    + $ npm install
    <!-- + $ npm run dev -->
    + $ npm run prod
16. Para editar **.env**:
    + $ nano .env
17. Reiniciar el servidor de apache:
    + $ sudo service apache2 restart
18. Para ver el estatus del servidor apache:
    + $ sudo service apache2 status

### Instalar y configurar MySQL en el servidor web:
1. Instalar MySQL:
    + $ sudo apt update
    + $ sudo apt install mysql-server
    + $ mysql
    + > CREATE DATABASE fid;
2. mmm






### Fix: Configuración del servidor web
1. Ingresar al archivo de configuración de apache en la terminal ftp:
    + $ sudo nano /etc/apache2/apache2.conf
2. Comentar las siguientes líneas con #:
    ```conf
    # User ${APACHE_RUN_USER}
    # Group ${APACHE_RUN_GROUP}
    ```
3. A continuación agregar las líneas:
    ```conf
    # User ubuntu
    User root
    Group ubuntu
    ```
4. Cambiar el siguiente bloque de códgio:
    ```conf
    <Directory /var/www/>
        Options Indexes FollowSymLinks
        AllowOverride None
        Require all granted
    </Directory>
    ```
    Por:
    ```conf
    <Directory /var/www/>
        Options Indexes FollowSymLinks
        AllowOverride All 
        Require all granted
    </Directory>
    ```
5. Para guardar los cambios:
    + $ Ctrl + X
    + $ y
    + $ ENTER
6. Habilitar modo rewrite:
    + $ sudo a2enmod rewrite
7. Reiniciar el servidor de apache:
    + $ sudo service apache2 restart
1. Para ver el estatus del servidor apache:
    + $ sudo service apache2 status



### Ajustes finales
1. Ingresa a la terminal y escribe:
    + $ sudo nano /etc/apache2/sites-enabled/000-default.conf
2. Al editar el archivo anterior añadir las siguientes reglas:
    + RewriteEngine On
    + RewriteCond %{HTTP:X-Forwarded-Proto} =http
    + RewriteRule .* https://%{HTTP:Host}%{REQUEST_URI} [L,R=permanent]
    + **Nota**: añadir al final del archivo y antes del cierre de </VirtualHost>
    + Salvar el archivo: 
        + $ Ctrl + X
        + $ y
        + $ ENTER
3. Reiniciar el servidor de apache:
    + $ sudo service apache2 restart








## Deploy en DigitalOcean
1. Ir a [DigitalOcean](https://cloud.digitalocean.com/login)
2. Click en **Create > App**.
3. Seleccionar el repositorio GitHub: **prueba-laravel-monogo-2022**.
4. Seleccionar la rama **main** y clickear en **Autodeploy** y click en **Next**.
5. Ajustar datos del formulario:
    + Type: Web Services
    + Environment Variables:
        + APP_ENV=production
        + APP_DEBUG=false
        + APP_KEY=base64:WOUjUbU6cQ8foyIL/8ssOpFgLmG7WxfBi/xSXJ0O5kg=
    + Build Command: 
        + composer install --no-dev --no-interaction --prefer-dist --optimize-autoloader
        + php artisan optimize
    + Run Command: heroku-php-apache2 public/
    + HTTP Port: 8080
6. Click en **Next**.
7. Rellenar formulario:
    + Name: prueba-laravel-monogo-2022
    + Region: Seleccionar la más cercana (normalmente es la que viene por defecto)
8. Click en **Next**.
9. Seleccionar plan, RAM y CPU y click en **Launch Basic App**.


10. Click en **Create > Database**.
11. Seleccionar **Mongo DB**.
12. Obtener credenciales:
    ```
    Public Network
    username = doadmin
    password = ***********
    host = mongodb+srv://db-mongodb-nyc3-12324-99e35dae.mongo.ondigitalocean.com
    port = 27017
    database = admin

    VPC Network
    username = doadmin
    password = ***********
    host = mongodb+srv://private-db-mongodb-nyc3-12324-13ad9ea2.mongo.ondigitalocean.com
    port = 27017
    database = admin
    ```


13. Para agregar las credenciales de la base de datos como variables de entorno:
    + Ir a la pestaña **Overview** y seleccionar la apliciación.
    + Environment Variables:
        + DB_CONNECTION=mongodb
        + DB_HOST=mongodb+srv://db-mongodb-nyc3-12324-99e35dae.mongo.ondigitalocean.com
        + DB_PORT=27017
        + DB_DATABASE=admin
        + DB_USERNAME=doadmin
        + DB_PASSWORD=**********
    + Click en **Save**. (Esperar a que se ejeucte el deploy)




15. Ir a **Settings**, seleccionar el proyecto y agregar las siguientes intrucciones en **Commands > Build Command**:
    + php artisan storage:link
    + php artisan migrate --force
    + npm install
    + npm run prod
16. Para el almacenamiento masivo se recomienda usar **Sapces Object Storage** de DigitalOcean o Amazon S3.
17. Referencias:
    + https://aprendible.com/series/aprende-laravel-intermedio/lecciones/como-publicar-una-aplicacion-de-laravel-en-digital-ocean-app-platform
    + https://programacionymas.com/blog/hacer-deploy-app-laravel-digital-ocean





18. Click en **Add a Database**.
    + Choose Name: db
    + Click en **Add Database**.


DB_CONNECTION=mongodb
DB_DSN=""
DB_PORT=27017
DB_DATABASE=admin
DB_USERNAME=doadmin
DB_PASSWORD=***


DB_DSN="mongodb+srv://petrix:xiphos333@cluster0.7y5of.mongodb.net/myFirstDatabase?retryWrites=true&w=majority"


php artisan cache:clear
php artisan config:clear
php artisan config:cache

mongodb+srv://doadmin:<replace-with-your-password>@db-mongodb-nyc3-12324-99e35dae.mongo.ondigitalocean.com/admin?authSource=admin&replicaSet=db-mongodb-nyc3-12324&tls=true&tlsCAFile=<replace-with-path-to-CA-cert>

mongodb+srv://doadmin:<replace-with-your-password>@db-mongodb-nyc3-12324-99e35dae.mongo.ondigitalocean.com/admin?authSource=admin&replicaSet=db-mongodb-nyc3-12324&tls=true&tlsCAFile=ca-certificate.crt