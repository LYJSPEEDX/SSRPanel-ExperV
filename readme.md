# SSRPanel
A set of achievement about freedom and blood.

## Installtion Tutorial
#### 1.bt.cn
Install the panel  
Enable **curl、gd、fileinfo、openssl** components  
Enable all functions which **start with 'proc_'** (from 'disable_function' configuration)  
Establish a new website, set relevant configuration(floder)
Add rewirte rules of 'Laravel'   
```
location / {
    try_files $uri $uri/ /index.php$is_args$args;
}
```

#### 2.Git clone
```
cd ssrpanel/
php composer.phar install
php artisan key:generate
chown -R www:www storage/
chmod -R 777 storage/
```

#### 3.Database initialization
Establish a database in 'utf8mb4'  
Import the sql file from 'sql' folder  

#### 4.Modify the core configuration file of ssrpanel
database/app(disable debug)/mail

#### 5.Add timed task via crontab
use the same role as ssrpanel
```
crontab -e -u www
* * * * * php /home/wwwroot/ssrpanel/artisan schedule:run >> /dev/null 2>&1
```
