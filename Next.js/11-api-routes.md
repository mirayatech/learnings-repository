# 🚀 Effortless API Routes

## 📁 The Special File: route.js|ts

In Next.js, there's a special file called `route.js|ts`, but it's only found within the app directory. These route handlers are like API routes in the pages directory. You usually don't need both for a single route. Here's how to define one:

```tsx
// app/api/route.ts
export async function GET(request: Request) {}
```

Keep in mind that `route.js` can't live alongside a `page.js` in the same route segment. However, it can nest within the app directory, just like `page.js` and `layout.js`.

## 🌐 The HTTP Methods

Route Handlers can handle a variety of HTTP methods, including `GET`, `POST`, `PUT`, `PATCH`, `DELETE`, `HEAD`, and `OPTIONS`. If you try to use an unsupported method, Next.js will let you know with a polite (or not so polite) 405 Method Not Allowed response.

## 🛠️ The Extended APIs

In addition to the native Request and Response, Next.js offers `NextRequest` and `NextResponse`. These come with helpful tools for advanced use cases.

## 🔄 The Behavior

Now, depending on how you use these APIs, Route Handlers can be static or dynamic.

### ⚙️ Static Route Handlers

By default, Route Handlers are statically evaluated when you use the `GET` method with the Response object. Here's a simple example:

```tsx
// app/items/route.ts
import { NextResponse } from "next/server";

export async function GET() {
  const res = await fetch("<https://data.mongodb-api.com/>...", {
    headers: {
      "Content-Type": "application/json",
      "API-Key": process.env.DATA_API_KEY,
    },
  });
  const data = await res.json();

  return NextResponse.json({ data });
}
```

Even though `Response.json()` is technically valid, TypeScript might throw a fit, so it's safer to use `NextResponse.json()` instead.

### 🔄 Dynamic Route Handlers

On the flip side, Route Handlers are evaluated dynamically when:

- Using the Request object with the `GET` method
- Using any other HTTP method
- Using Dynamic Functions like cookies and headers
- Manually specifying dynamic mode in the Segment Config Options

Here's a dynamic example:

```tsx
// app/products/api/route.ts
import { NextResponse } from "next/server";

export async function GET(request: Request) {
  const { searchParams } = new URL(request.url);
  const id = searchParams.get("id");
  const res = await fetch(`https://data.mongodb-api.com/product/${id}`, {
    headers: {
      "Content-Type": "application/json",
      "API-Key": process.env.DATA_API_KEY,
    },
  });
  const product = await res.json();

  return NextResponse.json({ product });
}
```

## 🚦 Some Ground Rules

Before we continue, it's important to note that each `route.js` or `page.js` file takes over all HTTP verbs for that route. So, for instance, if you have a `page.js` and a `route.js` in the same directory, that's going to cause a conflict. But, you can have `page.js` and `api/route.js` living together in harmony, no conflicts there!

## 🔄 Route Handlers and Other Features

Route handlers don't just stand alone - they interact with many other features and APIs in Next.js. They work with dynamic functions like cookies and headers, and they can handle different types of responses like redirects and dynamic route segments. Route handlers can even work with streams!

For instance, you can read cookies using the `cookies` function from `next/headers`:

```tsx
// app/api/route.ts
import { cookies } from "next/headers";

export async function GET(request: Request) {
  const cookieStore = cookies();
  const token = cookieStore.get("token");

  return new Response("Hello, Next.js!", {
    status: 200,
    headers: { "Set-Cookie": `token=${token}` },
  });
}
```

## 💼 Non-UI Responses

Not everything has to be about UI, you know. You can use Route Handlers to return non-UI content as well. For example, you can generate a sitemap.xml or a robots.txt. Heck, you could even return app icons or open graph images.

```tsx
// app/rss.xml/route.ts
export async function GET() {
  return new Response(`<?xml version="1.0" encoding="UTF-8" ?>
<rss version="2.0">

<channel>
  <title>Next.js Documentation</title>
  <link><https://nextjs.org/docs></link>
  <description>The React  Framework for the Web</description>
</channel>

</rss>`);
}
```

## ⚙️ Config Options

Lastly, don't forget about the segment config options. Just like pages and layouts, route handlers can be configured with various settings like `dynamic`, `dynamicParams`, `revalidate`, `fetchCache`, `runtime`, and `preferredRegion`.

And there you have it! That's your thorough rundown of API route handlers in Next.js 13. Happy coding!
