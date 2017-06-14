# docker-api-console
[![](https://images.microbadger.com/badges/version/joshuamarquez/api-console:0.1.1.svg)](https://microbadger.com/images/joshuamarquez/api-console:0.1.1 "Get your own version badge on microbadger.com") [![](https://images.microbadger.com/badges/image/joshuamarquez/api-console:0.1.1.svg)](https://microbadger.com/images/joshuamarquez/api-console:0.1.1 "Get your own image badge on microbadger.com")

Docker image for https://github.com/mulesoft/api-console

## Install

```bash
$ docker pull joshuamarquez/api-console
```

## Quick example

```bash
$ docker run -p 9000:9000 -p 35729:35729 -d joshuamarquez/api-console
```
then go to `http://localhost:9000` and you will see the example RAML API.

## Use own RAML files

This image will load RAML file `api.raml` located in container at `/api-console/dist/raml`, so to 
replace it and even add you own RAML files structure just mount a `VOLUME` like below.

```bash
docker run -v $(pwd):/api-console/dist/raml -p 9000:9000 -p 35729:35729 -d joshuamarquez/api-console
```

**Notes**

*  For the command above to work a RAML file named `api.raml` should exists in the directory were command was ran the same for any types, traits, securitySchemes, resourceTypes, etc.
*  Any changes to RAML files mounted will be reflected instantly, thats why PORT 35729 needs to be exposed (livereload).
