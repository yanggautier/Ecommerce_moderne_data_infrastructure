FROM python:3.10-slim


WORKDIR /opt/dagster/app

# Configuration de l'environnement Dagster
ENV DAGSTER_HOME=/opt/dagster/app

# Copier les fichiers de configuration
COPY workspace.yaml .
COPY requirements.txt ./requirements.txt
COPY ecommerce_pipeline ./ecommerce_pipeline

# Installer les dépendances
RUN pip install -r requirements.txt
# Exposer le port pour Dagit
EXPOSE 3000

# Commande par défaut
CMD ["dagit", "-h", "0.0.0.0", "-p", "3000"]