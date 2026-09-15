# NestJS API Starter

A practical, production-oriented NestJS 12 baseline using native ESM and pnpm.

## Included

- API prefix and URI versioning (`/api/v1`)
- Health endpoint at `GET /api`
- Swagger UI at `GET /docs`
- Environment validation with Joi
- Global request validation, transformation, and unknown-field rejection
- Helmet security headers, configurable CORS, and rate limiting
- Vitest unit/e2e test setup
- Multi-stage Docker image and Compose file

## Start locally

```bash
cp .env.example .env
pnpm install
pnpm start:dev
```

Open `http://localhost:3000/api` for health information and `http://localhost:3000/docs` for the API reference.

## Commands

```bash
pnpm build
pnpm lint
pnpm test
pnpm test:e2e
pnpm test:cov
pnpm start:prod
```

## Docker

```bash
docker compose up --build
```

## Configuration

Copy `.env.example` to `.env`. In production, set `NODE_ENV=production` and replace `CORS_ORIGIN=*` with a comma-separated list of trusted frontend origins.

## Suggested feature structure

Keep business code in self-contained modules:

```text
src/
  modules/
    users/
      dto/
      users.controller.ts
      users.service.ts
      users.module.ts
```

Add persistence deliberately (Prisma, TypeORM, etc.) after selecting your database; this starter intentionally does not couple the API to one.
