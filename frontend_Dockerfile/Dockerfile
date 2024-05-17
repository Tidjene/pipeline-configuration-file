# Utilisez une image Python officielle en tant qu'image de base
FROM python:3.9-slim

RUN apt-get update && apt-get install git -y
# creation d'environnement virtuel et activation
RUN python3 -m venv .venv && . .venv/bin/activate

ENV PATH="/.venv/bin:$PATH"

RUN pip install --upgrade pip
RUN pip install gunicorn
RUN git clone https://github.com/KhouloudBrn/YourImaginaryFriend.git

#permission des fichiers
RUN chmod -R 755 YourImaginaryFriend

WORKDIR "/YourImaginaryFriend/chatbot-main/"
#suppression de la base de donées d'index 
RUN rm -rf handbook_faiss

# Installation des dépendances de l'application Flask
RUN pip install -r requirements.txt


EXPOSE 10000

# Commande pour exécuter l'application Flask lorsque le conteneur démarre
CMD ["gunicorn", "-b", "0.0.0.0:10000", "rag_langchain_web:app"]