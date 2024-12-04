
# ⚡django-quickstart

django-quickstart is a simple Django application designed to simplify your development process. It provides a ready-to-use **landing page**, built-in **authentication**, and a **dashboard**. For a smoother development experience, it includes **django-auto-reload** to enable hot reloading and **django-tailwind** for immediate use of TailwindCSS.

The app is equipped with **Postgres** support, which allows for easy transition to a production-ready database as you prepare for deployment. Additionally, **AWS S3** configuration is available for serving static files in production environments.

django-quickstart aims to streamline the setup process for new Django projects by providing a ready-made foundation with essential features, saving developers time and effort.
  


## Features

This Django template is intentionally minimalistic, containing three pre-configured apps: **landing_page**, **accounts**, and **dashboard**.

1. **landing_page**: Acts as the homepage for your application, and can be further customized to meet your requirements.

2. **accounts**: Provides user registration, login, and logout capabilities to your application.

3. **dashboard**: Directs users to this app post-login/registration, where you can expand on your application’s functionality.

Key production-ready features include:

1. **Postgres support**: Allows for easy transition to a PostgreSQL database for production environments.

2. **AWS S3 support**: Facilitates configuring S3-compatible storage for serving static files in production.

The template is also equipped with the following pre-installed Python packages:

1. [**django-auto-reload**](https://github.com/adamchainz/django-browser-reload): Offers hot reload functionality to streamline your development process.

2. [**django-tailwind**](https://django-tailwind.readthedocs.io/en/latest/installation.html): Provides built-in support for using TailwindCSS.

## Requirements

To use this template you'll need to have the following installed:

1. Python 3
2. Latest version of NodeJS (https://nodejs.org/en)

## Setup

To begin using this template, start by creating a directory for your project:

    mkdir <YOUR_PROJECT_NAME>
    cd <YOUR_PROJECT_NAME>

Clone the repository into the current directory:

    git clone git@github.com:michael-awe/django-template.git .

Next, create and activate a virtual environment

    python3 -m venv env
    source env/bin/activate

Now install the dependencies from requirements.txt

    pip install -r requirements.txt

After installing the requirements, run setup.sh. You will then be prompted to enter a new project name. **Please ensure that the project name you enter is unique to ensure no clashes with Django or other Python modules**:

    sh setup.sh

Next, install tailwind by running the following command:

    python manage.py tailwind install

Next, create a `.env` file in the root directory of your project(same level as manage.py) and add the following secrets. It should look just like `.env.example` :

    DEBUG="True"
    SECRET_KEY="k=1opvz^^jopszbbzspxy(x45d_v0%ylhzbsr!05)!=_lihxz7"


## Usage

In order to use Tailwind, you'll have to create two terminal tabs, one to start tailwind and the other to start your Django server


In the first terminal enter the following command to get tailwind running:

    python manage.py tailwind start

You can then start your Django server in a separate tab with this command:

    python manage.py runserver

You're now all set and ready to start developing!


### Adding Tailwind to additional templates

By default, the landing_page, accounts and dashboard apps all have Tailwind integrated in their respective base.html files.

However, if you'd like to create a new app and add Tailwind support, either inherit from the base.html files of the other apps or add the following tags to your new HTML templates:

```

{% load static tailwind_tags %}

...

<head>

...

{% tailwind_css %}

...

</head>

```


### Configuring Postgres

This template is pre-configured for Postgres functionality. While the application operates with SQLite in DEBUG mode, switching DEBUG to False enables Postgres. To ensure it functions correctly, the following environment variables need to be defined in your .env file:

```plaintext

DB_NAME=""

DB_USER=""

DB_PASSWORD=""

DB_HOST=""

DB_PORT=""

```

### Configuring AWS S3

The template is also pre-configured for S3 storage to host static files. Like with Postgres, setting DEBUG to False in your environment variables activates S3 storage. To use this feature, ensure these environment variables are in your .env file:

```plaintext

AWS_ACCESS_KEY_ID="AWS_ACCESS_KEY_ID"

AWS_SECRET_ACCESS_KEY="AWS_SECRET_ACCESS_KEY"

AWS_STORAGE_BUCKET_NAME="AWS_STORAGE_BUCKET_NAME"

AWS_S3_SIGNATURE_VERSION="s3v4"

AWS_S3_REGION_NAME="eu-north-1"

```

This setup is optimized for AWS S3, though minor adjustments can allow compatibility with other S3-like storage solutions such as Cloudflare R2 and DigitalOcean Spaces. For further details, refer to the documentation at [django-storages](https://django-storages.readthedocs.io/).

## Contributing

If you would like to contribute to this repository or notice any issues with the code, please feel free to fork this repository and submit your changes in a pull request. Any contributions that improve the functionality or usability of the project are welcome.


## License

Django Template is licensed under the MIT License, which means that you are free to use, modify, and distribute the project as you see fit. See the LICENSE file for more information.
