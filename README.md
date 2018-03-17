# homestead-laravel
a laravel project inside a homestead vagrant box

# add appache to the VM

see [SO:A](https://stackoverflow.com/a/49339847/2245329)

As for now, to make a site entry in Homestead.yaml file works with Apache2, you need to:

1- Add the site to `Homestead.yaml`, with `type: apache` 
as fellow

    sites:
        -
            map: homestead.test
            to: /home/vagrant/code/Laravel/public    
        -
            map: homestead.test
            to: /home/vagrant/code/Apache/public
            type: apache



2- go to the vagrant box directory, and run

    vagrant destroy

3- then run

    vagrant up

4- shh to the vagrant machine

    vagrant ssh

5- flip the server, by running:

    flip

you'll get this message:

    nginx stopped
    apache started

## To test

I've created the directory Apache/public

    mkdir -p Apache/public

then inside it, I've created the file index.php

    echo "<?php phpinfo();" > Apache/public/index.php
 
Which is accessible using the same IP address of the default homestead negix site


