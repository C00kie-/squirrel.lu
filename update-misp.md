# Update a Misp (to last released version)

## Interface

## Where should I go to update my misp?

You must be admin,

Go to 
~~~
Administration > Server Settings & Maintenance > Diagnostics > there you are
~~~

You run the update request, you are aware that any modification done to your own instance will be lost. One the fetch is done and the version checked, it runs the update.

## If you have a denied:

~~~
cd $(git rev-parse --show-toplevel) && git checkout app/composer.json 2>&1

warning: unable to access '.git/config': Permission denied
fatal: unable to access '.git/config': Permission denied

cd $(git rev-parse --show-toplevel) && git pull origin '2.4' 2>&1

warning: unable to access '.git/config': Permission denied
fatal: unable to access '.git/config': Permission denied
warning: unable to access '.git/config': Permission denied
fatal: unable to access '.git/config': Permission denied

=================================

cd $(git rev-parse --show-toplevel) && git submodule sync 2>&1

warning: unable to access '/var/www/MISP/.git/config': Permission denied
fatal: unable to access '/var/www/MISP/.git/config': Permission denied

=================================

cd $(git rev-parse --show-toplevel) && git submodule update --init --recursive 2>&1

warning: unable to access '/var/www/MISP/.git/config': Permission denied
fatal: unable to access '/var/www/MISP/.git/config': Permission denied
~~~

Log in root;

## From the VM itself:

in root:

~~~
 cd /var/www/MISP
 git pull origin 
 git submodule update # 4 bis update MISP taxonommies, objects and galaxies from UI
~~~

# Update Galaxies and Objects

From UI:
~~~
Galaxies > Update Galaxies
Global Actions > List Object Templates > Update Objects 
~~~



