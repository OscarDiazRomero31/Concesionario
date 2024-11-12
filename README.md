# Concesionario
Proyecto Servidor

# Pasos para crear el proyecto y Comandos necesarios
IMPORTANTE LO PRIMERO AÑADIR EL README Y AÑARIR ARCHIVO DE REPOSITORIO DE JORGE

python3 -m venv myvenv

source myvenv/bin/activate

python -m pip install --upgrade pip
    Dentro de la carpeta "nombre del proyecto", creamos el archivo “requirements.txt”
        Django~=5.1.1

pip install -r requirements.txt
django-admin startproject mysite .
    Para configurar el proyecto debemos editar el archivo .settings.py:
        TIME_ZONE = ‘Europe/Madrid’ -> Configuramos la hora y fecha del proyecto
        LANGUAGE_CODE = ‘es’ -> Configuramos el lenguaje del proyecto
        Estáticos! -> Configuramos la ruta de los archivos estáticos(CSS por ejemplo)
        STATIC_URL = '/static/'
        STATIC_ROOT = BASE_DIR / 'static'
        ALLOWED_HOSTS = ['127.0.0.1', '.pythonanywhere.com','0.0.0.0'] -> direcciones ips que necesitamos para que funcione el proyecto.

python manage.py migrate        //Crear BBDD.

python manage.py runserver      //Lanzar APP.

python manage.py startapp "nombre del proyecto"

En el archivo settings.py en el apartado de INSTALLED_APPS debemos añadir la aplicación blog:
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    '"nombre del proyecto"',
]

    HACER LOS MODELOS EN models.py

python manage.py makemigrations "nombre del proyecto"

python manage.py migrate "nombre del proyecto"

python manage.py createsuperuser        //Crear superusuario para poder acceder al admin (/admin)




# Pasos en Casa desde un proyecto ya creado por git
Descargar proyecto con GIT
sudo apt-get install python3-venv  -> Sino está instalado ya
No situamos en la carpeta 2daw
python3 -m venv myvenv -> Creamos el entorno
source myvenv/bin/activate
python -m pip install --upgrade pip
pip install -r requirements.txt
python manage.py migrate -> Creamos base de datos
python manage.py runserver 0.0.0.0:8080 -> Lanzamos el servidor

