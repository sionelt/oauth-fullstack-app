# AUTH FULLSTACK APP

## Client

### Installation
1. Navigate to client dir `cd client`
2. Install packages/dependencies `npm install`
3. Run local development `npm run serve`

### Deployment

[![Netlify Status](https://api.netlify.com/api/v1/badges/77178fbf-6a4c-41d6-89fe-ca4dc4b177fc/deploy-status)](https://app.netlify.com/sites/distracted-mccarthy-9b9840/deploys)

Deployment to Netlify is auto trigger on merged pull requests to `master` branch

SPA available at [https://distracted-mccarthy-9b9840.netlify.app](https://distracted-mccarthy-9b9840.netlify.app/?target=_blank)


## Google API
1. Create and get client ID by following this: https://developers.google.com/identity/sign-in/web/sign-in
2. Set `VUE_APP_GOOGLE_SIGN_IN_CLIENT_ID=[client_ID_here]` as a env in `client/.env`. `client/~.env` as a template.

## REST API

### Installation
1. Navigate to api dir `cd api`
2. Install packages/dependencies `npm install`
3. Run local development server `npm start:local`

### Deployment
- Install Heroku CLI `npm install -g heroku`
- Authenticate your Heroku account `heroku login`
- Create a heroku app `heroku create auth-oauth-rest-api`
- Connect git repo to Heroku remotely `heroku git:remote -a auth-oauth-rest-api`
- Push only the api dir to Heroku remote master `git subtree push --prefix api/ heroku master` or `npm run deploy`
- Set rest api endpoint `VUE_APP_REST_API_ENDPOINT=[heroku_app_endpoint_here]` as a env in `client/.env`. `client/~.env` as a template.
- View Heroku app logs `heroku logs --tail`

## Database
1. Create free tier MonogDB instance on Heroku `heroku addons:create mongolab:sandbox`
2. To get `MONGODB_URI` for driver connection `heroku config:get MONGODB_URI`:
    - Development: Set `MONGODB_URI=[mongodb_uri_here]` as a env in `api/.env`. `api/~.env` as a template.

## Local Development
From root dir `/`:
- Run REST API server locally on http://localhost:5000 `cd api && heroku local web` or `npm run start:api`
- Run Vue SPA locally on http://localhost:8080 `npm run start:client`
