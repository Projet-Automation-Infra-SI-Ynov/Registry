Créer un fichier daemon.json dans /etc/docker/

Ajouter cette ligne : 
``
{ "insecure-registries":["172.16.100.9:5000"] }
``