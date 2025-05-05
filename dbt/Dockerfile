FROM python:3.10-slim

ENV HOME=/root
WORKDIR /dbt

RUN mkdir -p $HOME/.dbt
RUN chmod +x $HOME/.dbt


COPY profiles.yml $HOME/.dbt/profiles.yml

COPY . .
RUN pip install -r requirements.txt

# Utilisez --profile ecommerce_models pour spécifier explicitement le profil à utiliser
CMD ["sh", "-c", "dbt run --profiles-dir $HOME/.dbt --profile ecommerce_models"]