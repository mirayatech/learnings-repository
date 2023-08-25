# 🚀 Supercharged Middleware

## 🚦 What is Middleware?

Middleware is like a traffic cop at a bustling intersection. It directs traffic (requests) and can even modify their path.

Middleware gets to work before cached content and route matching. Its main job is to steer requests based on incoming data.

## 📜 Middleware File Convention

To use Middleware, create a file named `middleware.ts` (or `middleware.js`) in your project's root directory. That's the same level as `pages` or `app`, or inside `src` if you're using that structure.

Here's a basic example:

```tsx
// middleware.ts
import { NextResponse } from "next/server";
import type { NextRequest } from "next/server";

export function middleware(request: NextRequest) {
  return NextResponse.redirect(new URL("/home", request.url));
}

export const config = {
  matcher: "/about/:path*",
};
```

In this example, the middleware function intercepts every request and redirects it to the `/home` URL.

## 🔍 Matching Paths

Next.js Middleware runs for every route in your project, following this order:

1. Headers from `next.config.js`
2. Redirects from `next.config.js`
3. Middleware (rewrites, redirects, etc.)
4. `beforeFiles` (rewrites) from `next.config.js`
5. Filesystem routes (`public/`, `_next/static/`, `pages/`, `app/`, etc.)
6. `afterFiles` (rewrites) from `next.config.js`
7. Dynamic Routes (`/blog/[slug]`)
8. `fallback` (rewrites) from `next.config.js`

You have two ways to specify which paths Middleware will run on: custom matcher config and conditional statements.

### 🎯 Matcher

The `matcher` config lets you filter the Middleware to run on specific paths. It accepts either a single path or multiple paths with array syntax.

Here's an example:

```tsx
// middleware.ts
export const config = {
  matcher: ["/about/:path*", "/dashboard/:path*"],
};
```

In this case, Middleware will only run on paths that start with `/about/` or `/dashboard/`.

This config supports full regex, so you can do some nifty things like negative lookaheads or character matching.

```tsx
// middleware.ts
export const config = {
  matcher: ["/((?!api|_next/static|_next/image|favicon.ico).*)"],
};
```

This example matches all paths except the ones starting with `api`, `_next/static`, `_next/image`, and `favicon.ico`.

### 🎭 Conditional Statements

If you prefer to avoid regex or need more complex logic, you can use conditional statements within your Middleware function. Here's how:

```tsx
// middleware.ts
import { NextResponse } from "next/server";
import type { NextRequest } from "next/server";

export function middleware(request: NextRequest) {
  if (request.nextUrl.pathname.startsWith("/about")) {
    return NextResponse.rewrite(new URL("/about-2", request.url));
  }

  if (request.nextUrl.pathname.startsWith("/dashboard")) {
    return NextResponse.rewrite(new URL("/dashboard/user", request.url));
  }
}
```

In this case, any request that begins with `/about` gets rewritten to `/about-2`, and requests starting with `/dashboard` get rewritten to `/dashboard/user`.

## 🍪 NextResponse and Cookie Handling

The `NextResponse` API lets you redirect, rewrite, set headers, and manage cookies. It's also your tool for producing a response from Middleware directly.

When dealing with cookies, Next.js provides the `cookies` extension on `NextRequest` and `NextResponse`, allowing you to manipulate these cookies conveniently.

Here's an example of setting and reading cookies with Middleware:

```tsx
// middleware.ts
import { NextResponse } from "next/server";
import type { NextRequest } from "next/server";

export function middleware(request: NextRequest) {
  let cookie = request.cookies.get("nextjs")?.value;
  console.log(cookie); // => 'fast'

  request.cookies.delete("nextjs");
  request.cookies.has("nextjs"); // => false

  const response = NextResponse.next();
  response.cookies.set("vercel", "fast");
  cookie = response.cookies.get("vercel");
  console.log(cookie); // => { name: 'vercel', value: 'fast', Path: '/' }

  return response;
}
```

## 📦 Setting Headers

You can manipulate both request and response headers using the `NextResponse` API:

```tsx
// middleware.ts
import { NextResponse } from "next/server";
import type { NextRequest } from "next/server";

export function middleware(request: NextRequest) {
  const requestHeaders = new Headers(request.headers);
  requestHeaders.set("x-hello-from-middleware1", "hello");

  const response = NextResponse.next({
    request: {
      headers: requestHeaders,
    },
  });

  response.headers.set("x-hello-from-middleware2", "hello");
  return response;
}
```

## 🚀 Producing a Response

Middleware has the power to respond directly to a request. You can return a `Response` or `NextResponse` instance. This is especially useful if you need to authenticate a request or perform other checks before sending a response.

```tsx
// middleware.ts
import { NextRequest, NextResponse } from "next/server";
import { isAuthenticated } from "@lib/auth";

export const config = {
  matcher: "/api/:function*",
};

export function middleware(request: NextRequest) {
  if (!isAuthenticated(request)) {
    return new NextResponse(
      JSON.stringify({ success: false, message: "authentication failed" }),
      { status: 401, headers: { "content-type": "application/json" } }
    );
  }
}
```

## 🚀 Advanced Middleware Flags

Next.js v13.1 introduced two additional flags for advanced use cases: `skipTrailingSlashRedirect` and `skipMiddlewareUrlNormalize`.

`skipTrailingSlashRedirect` disables Next.js's default redirects for adding or removing trailing slashes, allowing for custom handling inside middleware.

`skipMiddlewareUrlNormalize` disables the URL normalization Next.js does to handle direct visits and client-transitions the same way, giving you full control over the original URL.
