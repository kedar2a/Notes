# Django at a glance

## Design your model:
- Although you can use Django without a database, it comes with an object-relational mapper in which you describe your database layout in Python code.

### Models:
- A model is the single, definitive source of information about your data. It contains the essential fields and behaviors of the data you’re storing. Generally, each model maps to a single database table
- **The basics**:
    * Each model is a Python class that subclasses django.db.models.Model.
    * Each attribute of the model represents a database field.
    * With all of this, Django gives you an automatically-generated database-access API
- **Using models**
    - changing the INSTALLED_APPS setting to add the name of the module that contains your models.py

#### **Fields**:
- Fields are specified by class attributes
- **Field types**:
    - Each field in your model should be an instance of the appropriate Field class
- **Field options**:
    - Each field takes a certain set of field-specific arguments

---

## [Migrations](https://docs.djangoproject.com/en/2.0/topics/migrations):
- Migrations are Django’s way of propagating changes you make to your models (adding a field, deleting a model, etc.) into your database schema. 

- There are several commands which you will use to interact with migrations and Django’s handling of database schema:

    1. `migrate`, which is responsible for applying and unapplying migrations.
    2. `makemigrations`, which is responsible for creating new migrations based on the changes you have made to your models.
    3. `sqlmigrate`, which displays the SQL statements for a migration.
    4. `showmigrations`, which lists a project’s migrations and their status.

- You should think of migrations as a version control system for your database schema. makemigrations is responsible for packaging up your model changes into individual migration files - analogous to commits - and migrate is responsible for applying those to your database.
- The migration files for each app live in a “migrations” directory inside of that app.
- Migrations will run the same way on the same dataset and produce consistent results
- Django will make migrations for any change to your models or fields - even options that don’t affect the database

- **Backend Support**:
    + Migrations are supported on all backends that Django ships with, as well as any third-party backends if they have programmed in support for schema alteration (done via the SchemaEditor class).
    + Django’s migration system is split into two parts; the logic for calculating and storing what operations should be run (`django.db.migrations`), and the database abstraction layer that turns things like “create a model” or “delete a field” into SQL - which is the job of the SchemaEditor.
    + *PostgreSQL* is the most capable of all the databases here in terms of schema support
    + *MySQL* lacks support for transactions around schema alteration operations, meaning that if a migration fails to apply you will have to manually unpick the changes in order to try again (it’s impossible to roll back to an earlier point).
    + *SQLite* has very little built-in schema alteration support

- **Workflow**:
    + Working with migrations is simple. Make changes to your models - say, add a field and remove a model - and then run makemigrations:
    + Your models will be scanned and compared to the versions currently contained in your migration files, and then a new set of migrations will be written out

- **Version control**: 
    + migrations are stored in version control, Django just cares that each migration has a different name.

- **Migration files**
    + Migrations are stored as an on-disk format, referred to here as “migration files”. These files are actually just normal Python files with an agreed-upon object layout, written in a declarative style.
    + What Django looks for when it loads a migration file (as a Python module) is a subclass of `django.db.migrations.Migration` called `Migration`. It then inspects this object for four attributes, only two of which are used most of the time:
        1. `dependencies`, a list of migrations this one depends on.
        2. `operations`, a list of Operation classes that define what this migration does.
- **[Model managers](https://docs.djangoproject.com/en/2.0/topics/migrations/#model-managers)**
    + You can optionally serialize managers into migrations and have them available in RunPython operations. This is done by defining a use_in_migrations attribute on the manager class:
- **Initial migrations**
    + **Migration.initial**
        * The “initial migrations” for an app are the migrations that create the first version of that app’s tables
- **Adding migrations to apps**
    + Adding migrations to new apps is straightforward - they come preconfigured to accept migrations, and so just run makemigrations once you’ve made some changes.
- **Adding migrations to apps**
- **Historical models**


---


## runserver: `django-admin runserver [addrport]`
- This server uses the WSGI application object specified by the `WSGI_APPLICATION` setting.
- **WSGI_APPLICATION**
    + Default: None
    + The full Python path of the WSGI application object that Django’s built-in servers (e.g. runserver) will use. The django-admin startproject management command will create a simple wsgi.py file with an application callable in it, and point this setting to that application.
    + If not set, the return value of django.core.wsgi.get_wsgi_application() will be used. In this case, the behavior of runserver will be identical to previous Django versions.
- If you are using Linux and install **pyinotify**, kernel signals will be used to autoreload the server (rather than polling file modification timestamps each second). This offers better scaling to large projects, reduction in response time to code modification, more robust change detection, and battery usage reduction