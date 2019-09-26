#on part de l'image apache
FROM mariadb

#on met à jour la machine et on installe ce qui manque
RUN apt-get update -yq \
#En production pas besoin de nano, en mode dev c'est quand même plus pratique pour débugguer
&& apt-get install nano -yq \
&& apt-get install git -yq \
&& apt-get clean -y

#on crée le répertoire de notre site web
#RUN mkdir /usr/local/apache2/htdocs/site1/
#on copie le dossier de notre site web dans le dossier adéquat d'apache2
#COPY ./site1/ /usr/local/apache2/htdocs/site1/
#on monte le dossier du site dans notre conteneur
#VOLUME /Users/fguntz/Programmation/VM/testDocker/apache-perso/site1/:/usr/local/apache2/htdocs/site1/
#on modifie le fichier de configuration d'apache2
#COPY ./my-httpd.conf /usr/local/apache2/conf/httpd.conf



