# Installation de l'environnement Web4Innovation


## Introduction

Vous avez reçu un poste de travail avec l'environnement de formation mise en place. Ce même environnement vous sera utile lors de vos projets sur la plateforme Web4Innovation.

Ce document couvre:

* La composition de l'environnement de dévelopement
* L'installation de l'environnement de développement
* Une section de références aux différents logiciels utilisé

## Composition de l'environnement

L'environnement de formation contient les programmes suivants:

```
formation
|-- Editeur
|-- Git
|-- VVV
|   |-- config
|   |-- database
|   |-- log
|   |-- provision
|   `-- www
|-- Vagrant
|   |-- box
|   |-- vagrant-hostsupdater
|   |-- vagrant-triggers
|   `-- vagrant-vbguest
|-- VirtualBox
`-- vv
```
	


Nous verrons dans plus de détailles après la mise en place de l'environnement quel est le role de chaque élément pour le moment voici une brève description

* `Editeur` vous trouverez l'éditeur `Sublime` qui permet d'éditer différents code source
* `Git` est logiciel de Source Control Management (SCM). Il vous permet de versionner votre code
* `VVV` permet de mettre en place tout l'environnement de développement web à partir du fichier `Vagrantfile` et des différents répertoire associés
* `Vagrant` automatise la création de machines virtuels et leur customisation
* `VirtualBox` est logiciel de virtualisation permettant de faire tourner des systèmes d'exploitations sur une machine hôte (votre PC)
* `vv` permet de créer une nouveau site web dans l'environnement `VVV`

## Installation

### Extension de virtualisation

Veuillez vérifier dans votre BIOS que l'extension VT-x est active. Nous avons besoin de cette extension pour pouvoir crée des machines virtuelles

### Windows

* Commencez tout d'abord par créer le répertoire `Formation2016` sur votre PC. Choisissez un emplacement ou vous pourrez le retrouver facilement même aprés la formation.
* Toutes les étapes de l'installation se font à partir du répertoire `Formation2016` que vous venez de créer
* Installer `Git-GUI` et `Git-Bash` à partir de l'installeur Windows `http://git-scm.com`
* Installer `VirtualBox` à partir de l'installeur Windows `www.virtualbox.com` qui se trouve dans le répertoire `VirtualBox`
* Lancer `VirtualBox` et ajouter le pack d'extension en double cliquant sur `Oracle_VM_VirtualBox_Extension_Pack` à télécharger sur `www.virtualbox.com`
* Installer `Vagrant` à partir de l'installeur Windows `www.vagrantup.com` qui se trouve dans le répertoire `Vagrant`
* Lancer l'invite de commande Windows (cmd) 
	* Installer `vagrant-hostsupdater` en executant `vagrant plugin install vagrant-hostsupdater`
	* Installer `vagrant-triggers` en executant `vagrant plugin install vagrant-triggers`
	* Installer `vagrant-vbguest` en executant `vagrant plugin install vagrant-vbguest`
* Cloner vv `https://github.com/bradp/vv` dans `Formation2016`
* Cloner VVV `https://github.com/Varying-Vagrant-Vagrants/VVV` dans `Formation2016`
* Ajouter `vv` au `PATH` windows
	* Ouvrir un explorateur de fichier et aller sur Mon Ordinateur.
 	* Faite un clique droit et choisissez les propriétés
 	* Choisissez les paramètres avancés
 	* Choisir les variables d'environnement dans l'onglet avancé
 	* Choisir la variable `PATH` et éditer la
 	* Ajouter un point virgule (`;`) à la fin du chemin d'accès précédent et ajouter le chemin vers le répertoire `vv` (Exemple: ;C:\Users\Name\Documents\formation\vv)
 	* Ouvrir Git Bash, rendez vous dans le répertoire `VVV` et exécuté `vv`
 	* Verifiez que vous n'obtenez aucune erreur
 * Créez votre machine virtuel avec votre environnement de développement en vous rendant dans le répertoire `VVV` et en exécutant `vagrant up`
 * Si tout les étapes se sont déroulé correctement vous devriez pouvoir ouvrir votre browser et vous rendre à l'adresse `vvv.dev`
 * Installer `Sublime` à partir de l'installeur Windows `www.sublimetext.com`


### Linux

Contactez nous si vous voulez utiliser Linux car la grande diversité d'environnement demande d'adapter les instructions. 

### OS X

* Commencez tout d'abord par créer le répertoire `Formation2016` sur votre PC. Choisissez un emplacement ou vous pourrez le retrouver facilement même aprés la formation.
* Toutes les étapes de l'installation se font à partir du répertoire `Formation2016` que vous venez de créer
* Installer `Git-GUI` et `Git-Bash` à partir de l'installeur OS X `http://git-scm.com`
* Installer `VirtualBox` à partir de l'installeur OS X `www.virtualbox.com` qui se trouve dans le répertoire `VirtualBox`
* Lancer `VirtualBox` et ajouter le pack d'extension en double cliquant sur `Oracle_VM_VirtualBox_Extension_Pack` à télécharger sur `www.virtualbox.com`
* Installer `Vagrant` à partir de l'installeur OS X `www.vagrantup.com` qui se trouve dans le répertoire `Vagrant`
* Lancer votre Terminal
	* Installer `vagrant-hostsupdater` en exécutant `vagrant plugin install vagrant-hostsupdater`
	* Installer `vagrant-triggers` en exécutant `vagrant plugin install vagrant-triggers`
	* Installer `vagrant-vbguest` en exécutant `vagrant plugin install vagrant-vbguest`
* Cloner vv `https://github.com/bradp/vv` dans `Formation2016`
* Cloner VVV `https://github.com/Varying-Vagrant-Vagrants/VVV` dans `Formation2016`
* Ajouter `vv` à votre `PATH`
	* Si vous utilisez `bash` vous devez éditer votre `.bashrc` qui se trouve dans votre répertoire personnel, typiquement `/Users/\<username\>/.bashrc`
	* Vous devez rajouter le chemin du répertoire `vv` à la variable `PATH`, ceci peut êtres fait comme suit dans le `.bashrc`: `export PATH=$PATH:/chemin/vers/vv`
	* Allez dans le répertoire `VVV` est exécuté `vv`
	* Verifier que vous n'obtenez aucune erreur
* Si toutes les étape se sont déroulé correctement vous devriez pouvoir ouvrir votre browser et vous rendre à l'adresse `vvv.dev`
* Installer `Sublime` à partir de l'installeur OS X `www.sublimetext.com`

## Références

### VVV

`VVV` ou `Varying Vagrant Vagrants` est un projet open source qui a pour but de créer un environnement de base pour les développeurs web `php` et tout particulièrement `wordpress`. Le projet s'appui sur `VirtualBox` comme logiciel open source pour la virtualisation et `Vagrant` pour automatiser la création d'une machine virtuelle `Ubuntu` et la customisation de la machine virtuelle en installant les logiciels nécessaires au développement `php` et `wordpress`.

Dans le cadre de cette formation et au vu de la quantité de logiciel à installer nous avons fait les modifications suivantes:

* Nous avons lancer la création et la customisation de base de `VVV`
* Nous avons crée une `Vagrant` box avec l'environnement installé dans `Vagrant/box`
* Nous avons modifier le fichier `Vagrantfile` afin qu'il référence la nouvelle box au lieu de la box de base `Ubuntu`

``` diff
diff --git a/vv b/vv
index 0b40fd3..277044f 100755
--- a/vv
+++ b/vv
@@ -753,7 +753,14 @@ PHP"
                        maybe_remove_defaults="wp theme delete twentythirteen --allow-root; wp theme delete twentyfourteen --allow-root; wp theme delete twentyfifteen --allow-root; wp plugin delete hello --allow-root; wp plugin delete akismet --allow-root; git checkout HEAD ."
                fi

-               install_method="wp core download --allow-root $installversion"
+                install_method="
+                if [ -z '$installversion' ] && [ -e /srv/www/latest.tar.gz ]; then
+                    tar -xf /srv/www/latest.tar.gz  && mv wordpress/* . && rm -rf wordpress
+                else
+                    wp core download --allow-root $installversion
+                fi
+                "
+
                config="wp core config --dbname=\"$db_name\" --dbuser=wp --dbpass=wp --dbhost=\"localhost\" --allow-root$wp_debug_text"
                core="wp core $install_text --url=$domain --title=\"$site\" --admin_user=$username --admin_password=$password --admin_email=$email --allow-root"
                if [ "$wpskeleton" = "true" ]; then
```

Ce changement test si l'archive de wordpress existe et l'utilise le cas échéant.

* Nous avons modifier le script de customisation qui se trouve dans `VVV/provision/provision.sh`

``` diff
diff --git a/provision/provision.sh b/provision/provision.sh
index de9e11f..d7b92e8 100755
--- a/provision/provision.sh
+++ b/provision/provision.sh
@@ -23,6 +23,8 @@ else
        echo "Network connection not detected. Unable to reach google.com..."
        ping_result="Not Connected"
 fi
+# Disabling connection to not update each time we re-provision
+ping_result="Not Connected"

 # PACKAGE INSTALLATION
 #
@@ -558,7 +560,6 @@ if [[ $ping_result == "Connected" ]]; then
                curl -L -O https://wordpress.org/latest.tar.gz
                tar -xvf latest.tar.gz
                mv wordpress wordpress-default
-               rm latest.tar.gz
                cd /srv/www/wordpress-default
                echo "Configuring WordPress Stable..."
                wp core config --dbname=wordpress_default --dbuser=wp --dbpass=wp --quiet --extra-php <<PHP
```

Le script de provisionning peut opérer en mode connecté et déconnecté. Dans le cas ou une connexion n'est pas disponible certaines parties de la customisation sont omises. Évidement la première customisation a besoin d'une connexion mais les suivantes ne font que mettre à jour les logiciels installés. Afin de rendre l'exécution plus rapide nous forçons le mode déconnecté. Si vous voulez mettre à jour votre environnement il vous suffit de commenter la modification comme suit `#ping_result="Not Connected"` et la décommenter une fois l'update fini.

La deuxième modification consiste à ne pas effacer l'archive wordpress télécharger pendant la customisation. Nous faisons cela car `vv` télécharge `wordpress` pour chaque nouveau site crée par default nous l’avons modifier pour qu'il puisse utilisé l'archive si elle existe. Les détailles de la modification sont expliqué dans la section `vv`.


Les logiciels installés sont les suivants:

1. [Ubuntu](http://www.ubuntu.com/) 14.04 LTS (Trusty Tahr)
1. [WordPress Develop](https://develop.svn.wordpress.org/trunk/)
1. [WordPress Stable](https://wordpress.org/)
1. [WordPress Trunk](https://core.svn.wordpress.org/trunk/)
1. [WP-CLI](http://wp-cli.org/) (master branch)
1. [nginx](http://nginx.org/) ([mainline](http://nginx.com/blog/nginx-1-6-1-7-released/) version)
1. [mysql](https://www.mysql.com/) 5.5.x
1. [php-fpm](http://php-fpm.org/) 5.5.x
1. [memcached](http://memcached.org/)
1. PHP [memcache extension](https://pecl.php.net/package/memcache)
1. PHP [xdebug extension](https://pecl.php.net/package/xdebug/)
1. PHP [imagick extension](https://pecl.php.net/package/imagick/)
1. [PHPUnit](https://phpunit.de/)
1. [ack-grep](http://beyondgrep.com/)
1. [git](http://git-scm.com/)
1. [subversion](https://subversion.apache.org/)
1. [ngrep](http://ngrep.sourceforge.net/usage.html)
1. [dos2unix](http://dos2unix.sourceforge.net/)
1. [Composer](https://github.com/composer/composer)
1. [phpMemcachedAdmin](https://code.google.com/p/phpmemcacheadmin/)
1. [phpMyAdmin](http://www.phpmyadmin.net/) (multi-language)
1. [Opcache Status](https://github.com/rlerdorf/opcache-status)
1. [Webgrind](https://github.com/jokkedk/webgrind)
1. [NodeJs](https://nodejs.org/)
1. [grunt-cli](https://github.com/gruntjs/grunt-cli)
1. [Mailcatcher](http://mailcatcher.me/)

### VVV

Le projet est hoster sur github à l'adresse suivante:

	https://github.com/Varying-Vagrant-Vagrants/VVV

### Vagrant

`Vagrant` est un logiciel permettant de créer, de configurer et de customiser des machines virtuels pour différent logiciel de virtualisation dont `VirtualBox`.

Le site du logiciel se trouve à l'adresse suivante:

	http://www.vagrantup.com

### VirtualBox

`VirtualBox` est un logiciel de virtualisation développé en open source par Oracle.

Le site du logiciel se trouve à l’adresse suivante:

	http://www.virtualbox.org

### vv

`vv` est un script qui automatise la création des différents répertoires et fichiers de configuration nécessaire à `VVV`. Il redémarre la VM de `VVV` et le script de customisation.

Le projet est hoster sur github à l'adresse suivante:
	
	https://github.com/bradp/vv

