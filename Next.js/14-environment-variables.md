# 🔒 Next.js Environment Variables: Keep Secrets Safe

Environment variables are your keys to security in Next.js. They let you store crucial info like API keys and database secrets outside your code. Here's how to master them in simple terms:

1. **Load .env.local**: Create a `.env.local` file in your project root. Put your secrets here, and they'll be available via `process.env`.

2. **Reference Others**: You can use `$` to refer to other env variables in your `.env` files, like `DB_FULL=$DB_USER:$DB_PASS`.

3. **Browser-Friendly**: To use env variables in the browser, add `NEXT_PUBLIC_` as a prefix. But be cautious; they become public.

4. **Defaults for Environments**: Set default env vars for different environments in `.env`, `.env.development`, and `.env.production`. `.env.local` rules them all.

5. **Vercel Setup**: For Vercel deployment, configure env vars in Project Settings and fetch them with the Vercel CLI for local development.

6. **Testing Environments**: Use `.env.test` for testing-specific env vars when `NODE_ENV` is 'test'. Keep it consistent.

7. **Loading Order**: Next.js follows a specific order when loading env vars. First `process.env`, then `.env.*.local`, `.env.local`, `.env.*`, and `.env`. It stops when it finds a match.

These simple steps keep your secrets safe, separate config from code, and make your app secure and scalable. 🚀🔐
