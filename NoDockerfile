# build stage
FROM node
COPY . /src
WORKDIR /src
RUN npm install
RUN npm run build

# run stage
FROM twalter/openshift-nginx:stable
RUN mkdir /mindmap
WORKDIR /mindmap/
COPY --from=0 /src/bin /config/www
EXPOSE 8081
