# Utiliser une image de base officielle de Python
FROM python:3.8-buster

# Définir le mainteneur de l'image
LABEL mainteneur="NGUEYEP Modeste Dolumin"

# Copier le code source de l'application dans l'image
COPY student_age.py /

# Mettre à jour les packages et installer les dépendances nécessaires
RUN apt-get update -y && \
    apt-get install -y python3-pip libldap2-dev libsasl2-dev && \
    pip install --upgrade pip

# Installer les packages Python nécessaires
RUN pip install python-ldap flask>=1.1.2 flask_httpauth>=4.1.0 flask_simpleldap python-dotenv>=0.14.0

# Créer un volume pour les données de l'application
VOLUME ["/data"]
COPY student_age.json /data/student_age.json
# Exposer le port que l'application utilisera
EXPOSE 5000

# Définir la commande à exécuter lorsque le conteneur démarre
CMD ["python", "/student_age.py"]
