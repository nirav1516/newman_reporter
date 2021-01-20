# Newman reporter

Supports newman-reporter-html and newman-reporter-htmlextra reporters apart from junit, json and cli

## Based on
[postman/newman](https://hub.docker.com/r/postman/newman) and [postmanLabs git](https://github.com/postmanlabs/newman/blob/develop/docker/images/alpine/Dockerfile)

## Build

Try it out by pulling locally:

```bash
docker build --build-arg NEWMAN_VERSION="full semver version" -t nirav1516/newman_reporter .
```

## Run local collection(linux):

```bash
# Mount host collections folder ~/collections, onto /etc/newman on the docker image, so that newman
# has access to collections
docker run -v ~/collections:/etc/newman -t nirav1516/newman_reporter \
run getcollection.postman_collection.json \
--reporters cli,junit,html,htmlextra \
--reporter-junit-export="newman-report.xml" \
--reporter-html-export="newman-html-report.html" \
--reporter-htmlextra-export="newman-htmlextra-report.html"
```

## Run local collection(windows):

```bash
# Mount host collections folder ~/collections, onto /etc/newman on the docker image, so that newman
# has access to collections
docker run -v C:\Users\collections:/etc/newman -t nirav1516/newman_reporter \
run getcollection.postman_collection.json \
--reporters cli,junit,html,htmlextra \
--reporter-junit-export="newman-report.xml" \
--reporter-html-export="newman-html-report.html" \
--reporter-htmlextra-export="newman-htmlextra-report.html"
```
