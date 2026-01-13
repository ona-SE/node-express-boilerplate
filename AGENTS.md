# node-express-boilerplate

Production-ready REST API boilerplate using Express and MongoDB, currently pinned to Node.js 12.

## Project Overview

A RESTful API boilerplate with authentication, validation, logging, testing, and Docker support. This repo is intentionally pinned to Node 12 to demonstrate Node.js version upgrade automation.

## Common Commands

- `yarn install` - Install dependencies
- `yarn dev` - Start development server with nodemon
- `yarn start` - Start production server with PM2
- `yarn test` - Run Jest test suite
- `yarn lint` - Run ESLint
- `yarn coverage` - Run tests with coverage

## Tech Stack

- **Runtime:** Node.js 12.x (needs upgrade to 20.x)
- **Framework:** Express 4.x
- **Database:** MongoDB with Mongoose 5.x
- **Auth:** Passport.js with JWT
- **Validation:** Joi
- **Testing:** Jest + Supertest
- **Linting:** ESLint + Prettier

## Node 12 Limitations

This repo is stuck on Node 12 which reached end-of-life in April 2022. Issues include:
- No security updates
- Missing modern JavaScript features
- Incompatible with newer package versions
- Performance improvements unavailable

## Upgrade Considerations

When upgrading to Node 20:
1. Update `engines` field in package.json
2. Update `.nvmrc` file
3. Update devcontainer.json image
4. Update CI/CD configurations (.travis.yml)
5. Check for deprecated APIs (Buffer constructor, etc.)
6. Update dependencies that require newer Node versions
7. Run full test suite to verify compatibility

## Architecture

```
src/
├── config/         # Environment and app configuration
├── controllers/    # Route controllers
├── middlewares/    # Express middlewares
├── models/         # Mongoose models
├── routes/         # API routes
├── services/       # Business logic
├── utils/          # Utility functions
└── validations/    # Joi validation schemas
```

## Database

Requires MongoDB running on localhost:27017. In Ona environments, this is started automatically via the automations.yaml service.

## Environment Variables

Copy `.env.example` to `.env` and configure:
- `MONGODB_URL` - MongoDB connection string
- `JWT_SECRET` - Secret for JWT signing
- `PORT` - Server port (default 3000)
