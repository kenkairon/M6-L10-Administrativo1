# Proyecto de Autenticación y Gestión de Usuarios
Proyecto Educativo
--

## Tabla de Contenidos
- [Requisitos](#requisitos)
- [Configuración del Entorno](#configuración-del-entorno)
- [Activación del Entorno](#Activación-del-Entorno)
- [Configuración Inicial](#configuración-inicial)
- [Pasos del Proyecto](#pasos-del-proyecto)
  - [Creación del Superusuario](#Creación-del-Superusuario)
  - [Configuración del Proyecto](#configuración-del-proyecto)
  - [Creación de Vistas y Modelos](#creación-de-vistas-y-modelos)

---
## Requisitos

- Python 3.9 o superior
- Django 4.0 o superior
- djangorestframework
---
## Configuración del Entorno

1. Crear el entorno virtual:
   ```bash
   python -m venv entorno_virtual 
   pip install -r requirements.txt
## Activación del Entorno

2. Activar el entorno virtual:
    ### Windows
    ```bash
    entorno_virtual\Scripts\activate

## Configuración Inicial
## Instalar Django y Guardar dependencias

3. Instalación Django
    ```bash
    pip install django

4. Instalación DRF
   ```bash
   pip install djangorestframework

5. Instalamos la actualizacion de pip
    ```bash
    python.exe -m pip install --upgrade pip

## Guardar las dependencias
6. Instalación dependencias
    ```bash
   pip freeze > requirements.txt

## Pasos del Proyecto
7. Crear el Proyecto
    ```bash
    django-admin startproject Autenticacion

8. Ingresar al directorio del Proyecto
    ```bash
    cd Autenticacion

9. Hacer las migraciones correspondientes y se va crear db.sqlite3
    ```bash
    python manage.py migrate

## Creación del superusuario
10. Creamos el super usuario , se refleja db.sqlite3 en auth_user , id , password, username
    ```bash
    python manage.py createsuperuser 

11. Por Motivos de aprendizaje y no de seguridad estas van hacer las credenciales 
    ```bash
    admin
    admin@gmail.com
    admin1234
    y

12. Activamos el servidor pero vamos a la siguiente ruta 127.0.0.1:8000/admin 
    ```bash
    python manage.py runserver

13. Creamos la Aplicación docs
    ```bash
    python manage.py startapp docs

14. Creamos la Aplicación front_user
    ```bash
    python manage.py startapp front_user

15. Creamos la Aplicación user_api
    ```bash
    python manage.py startapp user_api
## Configuración del Proyecto

16. Conectar el proyecto con la aplicación: Agregar 'docs','front_user','user_api', 'rest_framework' en la lista INSTALLED_APPS dentro del archivo autenticacion/settings.py
    ```bash
    INSTALLED_APPS = [
      'django.contrib.admin',
      'django.contrib.auth',
      'django.contrib.contenttypes',
      'django.contrib.sessions',
      'django.contrib.messages',
      'django.contrib.staticfiles',
      #Librerias Documentacion
      'rest_framework',
      'drf_spectacular',
      #Aplicaciones
      'user_api',
      'docs',
      'front_user',
    ]