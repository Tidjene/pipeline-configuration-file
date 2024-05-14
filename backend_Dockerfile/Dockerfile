FROM node:18

RUN apt-get update && apt-get install git -y

RUN git clone https://github.com/KhouloudBrn/pipeline-DevSecOps.git

WORKDIR /pipeline-DevSecOps/back

RUN npm install

COPY --chown=node:node . .

EXPOSE 3000

ENV HOST=0.0.0.0 PORT=3000

CMD ["node", "server.js"]
