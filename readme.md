# SSRPanel
A set of achievement about freedom and blood.

## Installtion Tutorial
#### 1.bt.cn
Install the panel  
Enable **curl、gd、fileinfo、openssl** components  
Enable all functions which **start with 'proc_'** (from 'disable_function' configuration)  
Establish a new website, set relevant configuration(floder)  
Add rewrite rules of 'Laravel'   
```
location / {
    try_files $uri $uri/ /index.php$is_args$args;
}
```

#### 2.Git clone and necessary configuration
Set everything absolutely correctly in .env file in root directory(rename from .env.example)   
**After modification, excute following codes**
```
php artisan cache:clear 
php artisan config:clear
```

#### 3.Database initialization
Establish a database in 'utf8mb4'  
Import the sql file from 'sql' folder  

#### 4.Process installtion
```
cd ssrpanel/
php composer.phar install
php artisan key:generate
chown -R www:www storage/
chmod -R 777 storage/
```

#### 5.Add timed task via crontab and run queue
use the same role as ssrpanel
```
crontab -e -u www
* * * * * php /home/wwwroot/ssrpanel/artisan schedule:run >> /dev/null 2>&1

sh queue.sh
```

#### Everything should work smoothly and safe

## Q&A:Customize images and other assets
#### logo/home_logo
~/public/assets/images/
#### footer
~/resources/views/user/layouts.blade.php  
~/resources/views/admin/layouts.blade.php
