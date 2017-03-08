# Pull the node image (boron version is the TLS version)
FROM node:boron

LABEL version="1.0"
LABEL description="Node Boron (TLS)"
LABEL author="PreciousDev"
LABEL authorURL="https://github.com/preciousDev"

RUN npm install -g webpack webpack-dev-server

# Create the app directory
RUN mkdir -p /usr/src/app1

# Any RUN command will be executed in this directory
WORKDIR /usr/src/app1

# Copy package.json into the app folder inside the container & install the app dependencies
COPY package.json /usr/src/app1/
RUN npm config set registry http://registry.npmjs.org/ && npm install

# Copy all app source into the app folder inside the container
COPY . /usr/src/app1

RUN webpack

# "The EXPOSE instruction informs Docker that the container listens on the specified network ports at runtime"
# https://docs.docker.com/engine/reference/builder/#expose
EXPOSE 3333

# Run the app using "npm start"
CMD [ "npm", "start" ]