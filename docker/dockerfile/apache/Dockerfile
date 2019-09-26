#on part de l'image apache
FROM php:7.3-apache

#on met à jour la machine et on installe ce qui manque
RUN apt-get update -yq \
#En production pas besoin de nano, en mode dev c'est quand même plus pratique pour débugguer
&& apt-get install vim -yq \
&& apt-get install git -yq \
&& apt-get clean -y \
#après installation il faut faire un service apache2 reload (ce qui est le cas à la fin du fichier)
&& docker-php-ext-install pdo_mysql \
#installation de xdebug
&& pecl install xdebug-2.7.2 \
&& pecl clear-cache

COPY ./xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini
#commande pas utile doit l'activer après l'installation à vérifier
#&& docker-php-ext-enable xdebug

#on crée le répertoire de notre site web a priori pas besoi
#RUN mkdir /var/www/html/site1/ \
#&& cd /var/www \
#&& chown -R www-data:www-data html/ \
#&& chmod -R 744 html/
#on copie le dossier de notre site web dans le dossier adéquat d'apache2
#COPY ./site1/ /usr/local/apache2/htdocs/site1/
#on monte le dossier du site dans notre conteneur
#VOLUME /Users/fguntz/Programmation/VM/testDocker/apache-perso/site1/:/usr/local/apache2/htdocs/site1/
#on modifie le fichier de configuration d'apache2
COPY ./site1.conf /etc/apache2/sites-available/site1.conf
#RUN /etc/init.d/apache2 reload
#service apache2 reload
RUN a2ensite site1.conf \
&& a2dissite 000-default.conf
#&& service apache2 reload \
#&& service apache2 reload

RUN service apache2 start

#CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]