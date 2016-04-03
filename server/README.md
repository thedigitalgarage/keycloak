# Keycloak Docker image

Example Dockerfile with Keycloak server on The Digital Garage.

## Usage

To boot in standalone mode

    oc new-app thedigitalgarage/keycloak

Once it boots, you can login to the admin console using admin/admin for the first login. If you have not created an admin account, use the instructions below to creat the admin account with enviroment variables at build.

## Creating admin account

By default there is no admin user created so you won't be able to login to the admin console. To create an admin account you need to use environment variables to pass in an initial username and password. This is done by running:

    oc new-app -e KEYCLOAK_USER=<USERNAME> -e KEYCLOAK_PASSWORD=<PASSWORD> thedigitalgarage/keycloak

### Specify log level

When starting the Keycloak instance you can pass a number an environment variables to set log level for Keycloak, for example:

    oc new-app -e KEYCLOAK_LOGLEVEL=DEBUG thedigitalgarage/keycloak

## Other details

This image extends the [`jboss/base-jdk`](https://github.com/JBoss-Dockerfiles/base-jdk) image which adds the OpenJDK distribution on top of the [`jboss/base`](https://github.com/JBoss-Dockerfiles/base) image. Please refer to the README.md for selected images for more info.
