FROM node:10
WORKDIR /usr/src/app

RUN npm install -g node-gyp
COPY . .
RUN mkdir -p record/src
RUN wget https://download.agora.io/ardsdk/release/Agora_Recording_SDK_for_Linux_v3.0.1.tar.gz
RUN tar xvfz Agora_Recording_SDK_for_Linux_*.tar -C record/src
RUN mv record/src/Agora_* record/src/sdk

WORKDIR /usr/src/app/record/src
RUN node-gyp clean
RUN node-gyp configure 
RUN node-gyp build


