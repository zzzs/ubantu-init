# ubantu-init
ubantu初始化配置

## git
  * sudo apt-get install git

## mongodb 127.0.0.1:27017
  * sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 9DA31620334BD75D9DCB49F368818C72E52529D4
  * echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/4.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.0.list
  * sudo apt-get update
  * sudo apt-get install -y mongodb-org

## redis 127.0.0.1:6379
  * sudo apt-get update
  * sudo apt-get install redis-server

## nginx 127.0.0.1:80
  * sudo apt-get install nginx
  * sudo service nginx restart

### php
  * sudo apt-get install php7.0-fpm php7.0-mysql php7.0-common php7.0-curl php7.0-cli php7.0-mcrypt php7.0-mbstring php7.0-dom
  * config
      - sudo vim /etc/php/7.1/fpm/php.ini: cgi.fix_pathinfo=0
      - sudo service php7.0-fpm restart

### composer
  * sudo curl -s https://getcomposer.org/installer | sudo php
  * sudo chmod a+x composer.phar
  * sudo mv composer.phar /usr/local/bin/composer
  * composer config -g repo.packagist composer https:/packagist.phpcomposer.com

### mysql 127.0.0.1:3306
  * apt-get -y install mysql-server mysql-client
  * CREATE USER 'xl'@'localhost' IDENTIFIED BY '123123';
      - grant all privileges on mq.* to test@localhost identified by '1234';
      - flush privileges;
  * remove
      - sudo apt-get autoremove --purge mysql-server-5.7 
      - sudo apt-get remove mysql-common
      - sudo rm -rf /etc/mysql/  /var/lib/mysql    #很重要
      - dpkg -l |grep ^rc|awk '{print $2}' |sudo xargs dpkg -P  
      - sudo apt autoremove
      - sudo apt autoreclean

### node 
  * wget https://npm.taobao.org/mirrors/node/v10.7.0/node-v10.7.0-linux-x64.tar.xz
  * sudo mv node-v10.7.0-linux-x64.tar.xz /usr/local/
  * sudo tar -xvf  node-v10.7.0-linux-x64.tar.xz
  * mv node-v10.7.0-linux-x64  nodejs
  * sudo ln -s /usr/local/nodejs/bin/node /usr/bin/
  * sudo ln -s /usr/local/nodejs/bin/npm /usr/bin/
