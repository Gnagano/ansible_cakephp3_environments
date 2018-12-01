# Ansible Role: create new cakephp3 application

Use this role when you create new cakephp3.

## Requirements

- OS: Ubuntu16.04
- php version is higher than 7.0
- The database for the new cakephp3 app is set

## Setup

```
$ ansible_galaxy install gano2018.ansible_cakephp3 --roles-path <your_roles_directory>
```

## Usage

Copy `defaults/main.yml.default` as `defaults/main.yml` and edit `main.yml`. The roles variables on main.yml are depends on you. Please read the next section `Role Varibles` below.
After editing main.yml, just execute main.yml

## Role Variables

#### php_version

  Set '7.0' if you use php version higher than 7.0, even though you use php7.1 or php7.2 and higher.

#### cakephp3_project_name

  The name of what you want to create app

#### cakephp3_app_dir

  The directory where your new app is installed.

#### cakephp3_required_packages

  The packages required to install cakephp3 app.

#### cakephp3_webserver_app

  The name of web server application you will use on server.
  If using nginx, make the value 'nginx'. If apache, value is 'apache'.

#### cakephp3_nginx_conf_file

  The file path for nginx conf file.
  The default value is `/etc/nginx/sites-enabled/default`

#### cakephp3_nginx_service_port

  The service port for nginx.
  The default value is `80`

#### cakephp3_email_host
#### cakephp3_email_port
#### cakephp3_email_address
#### cakephp3_email_password

  Those valiables are for email settings.
  As the name of variable, they will be set hostname, port, address, password.

#### cakephp3_db_default_driver
#### cakephp3_db_default_host
#### cakephp3cakephp3_db_default_username
#### cakephp3cakephp3_db_default_password
#### cakephp3cakephp3_db_default_database

  Those valiables are for database settings written on `config/app.php`
  As the name of variable, they will be set driver name, host, username, password and database name. The default value of `cakephp3_db_default_driver` is `Cake\Database\Driver\MySql`

#### cakephp3_db_test_default_driver
#### cakephp3_db_test_default_host
#### cakephp3cakephp3_db_test_default_username
#### cakephp3cakephp3_db_test_default_password
#### cakephp3cakephp3_db_test_default_database

  Those variables are for test database.
