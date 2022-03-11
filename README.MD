Créer un fichier daemon.json dans /etc/docker/

Ajouter cette ligne : 
``json
{ "insecure-registries":["172.16.100.9:5000"] }
``