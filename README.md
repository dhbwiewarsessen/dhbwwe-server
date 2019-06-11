# dhbwwe-server

This repository contains the files we use on our server for the DHBWieWarsEssen App. 

To setup your own server, just follow the installation guide below.

## Installation

### Acquire a server

To run our server you need to be able to host some php files public on your server, run a mysql database and execute cronjobs.
If you know how to do that, you can host it on your own machine. If you don't or you don't want to run it on your machine just use a free webhoster. 

We use [Googiehost](www.googiehost.com) for our server but you can use any webhoster and as long as it also provides cPanel, the installation should look the same.

### Setup the database

You can create the database on your server by just running our [sql-statement](dhbwwe_data.sql).

You also need to create a user to access the database from the php files. If you don't want to trouble yourself with changing the username and password in all the files, you can take 'dhbwwe_user' as username and 'jhgcwbncskijioihe' as password.

If you want to protect your database, you should obviously change at least the password.

### Setup the php files

You can find the php files [here](php/).

In each php file there is a mysqli_connect statement. You need to set this up for your server. 

```php
$con = mysqli_connect("localhost", "dhbwwe_user", "jhgcwbncskijioihe", "dhbwwe_data");
```

If your database doesn't run on the same computer as the php files, you need to change localhost to the adress of your database server.

If you use another username and password for your user, you need to change these in the php files aswell.

The last string is the name of the database. If you used our sql statement to create the database, you do not need to change that.

Once you have edited the connect statement for all your files, you just need to put them into the public_html directory on your server.

### Setup the cronjobs

tbd