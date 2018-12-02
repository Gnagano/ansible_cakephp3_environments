# Ansible Role: set up for cakephp-environments

## Overviews

This ansible roles allow you to install and setting [josegonzalez/cakephp-environments](https://github.com/josegonzalez/cakephp-environments)
You can change environment such like `develop`,`test`,`production`,`jenkins` in default settings.

## Requirements

- OS: Ubuntu16.04
- The database for the cakephp3 app is set

## Setup

Install the ansible roll from galaxy or git clone it.

```
$ ansible_galaxy install gano2018.ansible_cakephp3 --roles-path <your_roles_directory>
```

And then, copy `defaults/main.yml.default` as `defaults.yml` and edit the role variables.
About role variables, please checkt the next paragraph.

## Role variables you need to edit

#### cakephp3_project_name:

Please set the your project directory name for cakephp3.

#### cakephp3_app_dir:

This variable is the directory which has your cakephp3 project.
If your cakephp3 project name is `test` and the direcoty is in `/var/www/html/test`, so the variable is `/var/www/html`

#### cakephp3_webserver_app:

Set `nginx` if you use `nginx` ,otherwise specify your web server such as `apache`.

#### cakephp3_nginx_conf_dir:

The directory where config file for nginx. The default value is `/etc/nginx/sites-enabled`.

#### cakephp3_nginx_default_env:

Specify the name of environment you use in defulat. The default value is `development`.

#### cakephp3_test_name:

Specify the name of environment you use for test. The default value is `test`.

#### cakephp3_nginx_server_name:

Specify the name of access to the server such as domain name.
If you set `test.localhost`, you can access the server test.localhost end environment variable `CAKE_ENV` will be `cakephp3_test_name` when the app works.

### cakephp3_security_salt:

Plese set your app's security_salt which will be added in app.php

#### cakephp3_envs:

Please set the environments you need.
The default values are `[ 'development', 'test', 'jenkins' ]`

For example, add `production`  or `staging` if you need.

#### development_db_driver
#### development_db_host
#### development_db_username
#### development_db_password
#### development_db_name

`development` is the name of environment and please set db driver, db host, username, password and db name.
This variable is used in `template/development.php.j2` and will be copied to `/config/bootstrap/environments/development.php`

When you edit `test_db_driver`, you will see the same situation.
The variable is used in `template/test.php.j2` and will got to `/config/bootstrap/environments/test.php`

In the default setting, there are three environments, development, test and jenkins. So you need to edit database inforimation for three environments.

#### development_test_db_driver
#### development_test_db_host
#### development_test_db_username
#### development_test_db_password
#### development_test_db_name

Those are the same as previous variables, the difference are that this variables are describing about database for test.
Set the variables in the same way.

#### cakephp3_email_host
#### cakephp3_email_port
#### cakephp3_email_address
#### cakephp3_email_password

Those valiables are for email settings.
As the name of variable, they will be set hostname, port, address, password.

## Usage

After setting role varibles, just execute ansible role.
