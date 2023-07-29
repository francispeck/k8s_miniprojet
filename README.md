## k8s_miniprojet

- L’appli Wordpress est composé d’un front et d’un back, la partie BDD Mysql

- J’ai commencé par déployer un pod mysql, ce pod est dans un objet de type deployment avec un seul replicas

- Le pod mysql a un service de type clister ip pour pouvoir l’exposé en interne dans k8s.

- J’ai déployé également un pod wordpress qui est lui aussi dans un objet de type deployment et un service de type nodeport qui est le point d’entrée de l’appli c'est-à-dire il servira d’exposer l’appli à l’extérieur.

- L’appli va interroger la BDD en passant par le cluster ip

- J’ai également crée un stockage persistant pour mysql, j’ai simplement crée un volume qui est mis dans /data/mysql et c’est le /var/lib/mysql de mysql  qui y sera stocké

- J’ai également associé au pod wordpress un volume /data/wordpress qui va stocké le /var/www/html de wordpress

- J’ai également crée le namespace pour stocker et mieux gérer mes ressources.
