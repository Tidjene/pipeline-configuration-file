# Utilisez une image Python officielle en tant qu'image de base
FROM python:3.9-slim

RUN apt-get update && apt-get install git -y

RUN python -m venv .venv && . .venv/bin/activate

ENV PATH="/.venv/bin:$PATH"

RUN pip install --upgrade pip

RUN git clone https://github.com/KhouloudBrn/pipeline-DevSecOps.git


RUN chmod -R 755 pipeline-DevSecOps

WORKDIR "/pipeline-DevSecOps/1_welcome/interne/Serv 6 chatbot/chatbot-main/chatbot-main"

RUN rm -rf handbook_faiss

# Installez les dépendances de l'application Flask
RUN pip install --no-cache-dir -r requirements.txt

# Exposez le port sur lequel l'application Flask s'exécute
EXPOSE 5000

# Commande pour exécuter l'application Flask lorsque le conteneur démarre
CMD ["python", "rag_langchain_web.py"]