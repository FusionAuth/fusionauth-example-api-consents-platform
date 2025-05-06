# Example API Consents Application

This repo holds two example JavaScript applications. 

* MoneyScope, a financial analysis tool
* Changebank APIs

This application will use an OAuth Authorization Code Grant workflow to log a user in, request needed OAuth Scopes and get them access and
refresh tokens. The access token will be used to make a request against the Changebank APIs to find the user's balance.

This application was built to illustrate the [API Consents Platform use case](https://fusionauth.io/docs/get-started/use-cases/api-consents-platform).

## Project Contents

The `docker-compose.yml` file and the `kickstart` directory are used to start and configure a local FusionAuth server.

You must edit `kickstart/kickstart.json` with a [valid Essentials or Enterprise license key](https://fusionauth.io/pricing).

The `/moneyscope-application` directory contains a fully working version of the MoneyScope application.
The `/changebank-apis` directory contains a fully working version of the Changebank APIs.

## Project Dependencies
* Docker, for running FusionAuth
* Node 20.12.2 or later, for running the applications

## Running FusionAuth
To run FusionAuth, just stand up the docker containers using `docker-compose`.

```shell
docker compose up
```

This will start a PostgreSQL database, and Elastic service, and the FusionAuth server.

## Running the Apps

For the MoneyScope application:

```shell
cd moneyscope-application
npm install
npm run dev
```

In a separate terminal window, to start the Changebank APIs:

```shell
cd changebank-apis
npm install
npm run dev
```

## Testing Out the Apps

Visit the local webserver at `http://localhost:8080/` and sign in using the credentials:

* username: richard@example.com
* password: password

Accept the scopes and you'll be logged into the MoneyScope application.

You can modify the bank balance by changing the APIs in the `changebank-apis/routes/index.js` file.
