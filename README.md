NestJs - Authentication JWT
======================================
## Description
This project was to study nestjs and some extra technologies

- Nestjs support via [Nest](https://github.com/nestjs/nest)
- Passport support via [passport](https://www.npmjs.com/package/passport)
- Passaport JWT support via [passport-jwt](https://www.npmjs.com/package/passport-jwt)
- Passport Local support via [passport-local](https://www.npmjs.com/package/passport-local)

## Installation

```bash
$ yarn install
```
## Running the app

```bash
# development
$ yarn run start

# watch mode
$ yarn run start:dev

# production mode
$ yarn run start:prod
```

## API Documentation

```
$ # GET /profile
$ curl http://localhost:3000/profile
$ # result -> {"statusCode":401,"message":"Unauthorized"}

$ # POST /auth/login
$ curl -X POST http://localhost:3000/auth/login -d '{"username": "caio.almeida", "password": "12345"}' -H "Content-Type: application/json"
$ # result -> {"access_token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2Vybm... }

$ # GET /profile using access_token returned from previous step as bearer code
$ curl http://localhost:3000/profile -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2Vybm..."
$ # result -> {"userId":1,"username":"caio.almeida"}
```