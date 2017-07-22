# Install PostgreSQL

## macOS

**Using Postgres app for macOS**

Follow instructions here[https://postgresapp.com/](https://postgresapp.com/)to set it up on your computer

Once installed make sure the app is running and that you have the elephant icon in your taskbar. You should see`Running on port 5432`

**Using brew**

To install run the following command.

`brew install postgresql`

Starting postgres

`brew services start postgresql`

## Ubuntu

Head over to your terminal and execute the following commands

```
$ sudo sh -c "echo 'deb http://apt.postgresql.org/pub/repos/apt/ xenial-pgdg main' 
>
 /etc/apt/sources.list.d/pgdg.list"

$ wget --quiet -O - http://apt.postgresql.org/pub/repos/apt/ACCC4CF8.asc | sudo apt-key add -

$ sudo apt-get update
$ sudo apt-get install postgresql-common
$ sudo apt-get install postgresql-9.5 libpq-dev
```

## Create users

* Default user postgres

`createuser -s -r -P postgres`

You'll be prompted for a password enter`postgres`

* User matching your computer's username

`sudo -u postgres createuser <your_username> -s -r`

If you want to set a password for your user, set the`-P`flag with the above command

## Create database

`createdb <database-name>`

or

`psql -c "create database <database-name>"`

