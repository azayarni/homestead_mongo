# Laravel Homestead (v 0.3.3) with MongoDB

## Included software

- Ubuntu 14.04
- Git
- PHP 5.6
- Xdebug
- HHVM
- Nginx
- MySQL
- Sqlite3
- Postgres
- Composer
- Node (With PM2, Bower, Grunt, and Gulp)
- Redis
- Memcached (PHP 5.x Only)
- Beanstalkd
- MongoDB

## Installation

1. Install Virtual Box: https://www.virtualbox.org/wiki/Downloads

2. Install Vagrant: http://www.vagrantup.com/downloads.html

3. On console add homestead box:

   vagrant box add laravel/homestead --box-version 0.3.3

4. Create working directory e.g. ~/Dev/laravel and checkout this repository to "homestead" subfolder

   mkdir ~/Dev/laravel
   cd ~/Dev/laravel
   git clone git@github.com:azayarni/homestead_mongo.git homestead
   
   cd homestead
   bash init.sh
   
5. Edit Homestead configuration ~/.homestead/Homestead.yaml
   
   Set provider
   ```
   provider: virtualbox
   ```
   
   Map folders
   ```
   folders:
      - map: ~/Dev/laravel/code
        to: /home/vagrant/code
        type: "nfs"
   ```

   Configure site
   ```
   sites:
       - map: mysite.dev
         to: /home/vagrant/code/mysite.dev/public
   ```
   
6. Run Vagrant provision. It takes some time and hopefuly doesn't fail 

   vagrant up
   
7. Done? Now just add mysite.dev or whatever local domain you are using to the /etc/hosts file

   ```
   192.168.10.10  mysite.dev
   ```




