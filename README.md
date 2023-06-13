# GeoXACML 3.0 JSON Profile support
This package is a fork of the [Authzforce CE Rest-API-Model package](https://github.com/authzforce/rest-api-model/tree/custom-mediatype-geoxacml) for supporting GeoXACML 3.0 media types. The GeoXACML 3.0 media types `application/geoxacml+xml` and `applicaiton/geoxacml+json` are added.

The [GeoXACML 3.0 plugin for the Authzforce CE Server](https://github.com/securedimensions/authzforce-ce-geoxacml3) requires the JAR compiled from this repository.

## Compilation
Make sure JAVA 11 is installed and linked with Maven.

```shell
cd /opt
sudo git clone -b custom-mediatype-geoxacml https://github.com/securedimensions/authzforce-ce-geoxacml3-rest-api-model.git 
cd authzforce-ce-geoxacml3-rest-api-model
sudo mvn versions:set -DnewVersion=6.0.0-geoxacml
sudo mvn clean package
```
## Installation
To enable the GeoXACML media types, the existing Authzforce CE Rest-API-Model JAR must be removed and the generated JAR must be copied into the Authzforce CE webapp installation directory. The root directory of the Authzforce CE installation is considered to be `/opt/authzforce-ce-server`.

```shell
cd /opt/authzforce-ce-geoxacml3-rest-api-model
sudo rm /opt/authzforce-ce-server/webapp/WEB-INF/lib/authzforce-ce-rest-api-model-6.0.0.jar
sudo cp target/authzforce-ce-rest-api-model-6.0.0-geoxacml.jar /opt/authzforce-ce-server/webapp/WEB-INF/lib
```