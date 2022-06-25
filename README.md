# nextjs-starter

Kickstart your project with this simple but modern full-stack starter app.

## Technologies

- TypeScript as the programming language
- Next.js as the React framework
- Next.js API routes for server-side API routes as the backend
- Prisma for migrations and database access
- PostgreSQL as the database
- NextAuth.js for authentication via GitHub (OAuth)
- ESLint extended by Prettier for code style
- Vercel for deployment

Based on Vercel's own [Next.js Full-stack Starter](https://vercel.com/guides/nextjs-prisma-postgres).

## How to Start Locally

1. Clone the repository
2. Install dependencies with `yarn`
3. [Set up a local PostgreSQL database](https://www.prisma.io/dataguide/postgresql/setting-up-a-local-postgresql-database)
4. Rename `.env.template` to `.env` and update `DATABASE_URL` to your PostgreSQL database URL
5. [Create a GitHub OAuth app](https://docs.github.com/en/developers/apps/building-oauth-apps/creating-an-oauth-app), and update the env variables `GITHUB_ID` and `GITHUB_SECRET`
6. Run `yarn dev` to start the development server locally
7. Run `yarn prisma studio` to start the Prisma Studio UI

## How to Deploy

1. Fork this repository (or click the "Use this template" button)
2. Log in to Vercel and create a new project from the repository
3. [Set up a free PostgreSQL database on Heroku](https://dev.to/prisma/how-to-setup-a-free-postgresql-database-on-heroku-1dc1)
4. [Create another GitHub OAuth app](https://docs.github.com/en/developers/apps/building-oauth-apps/creating-an-oauth-app) for production, and update the env variables `GITHUB_ID` and `GITHUB_SECRET`
5. In Vercel, go to Project Settings > Environment Variables and set `DATABASE_URL` to your Heroku database URL, and `GITHUB_ID` and `GITHUB_SECRET` with your production GitHub OAuth app's credentials
6. Run `openssl rand -base64 32` to generate a random string and update the Vercel env variable `NEXTAUTH_SECRET` with the output, and update `NEXTAUTH_URL` to `https://you-domain.vercel.app/api/auth`
