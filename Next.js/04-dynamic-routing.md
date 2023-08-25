# 🔄 Dynamic Routing

Dynamic routing in Next.js is super useful. It lets you create routes when you don't know the names beforehand or when they come from data.

To make a route dynamic, just put square brackets around the folder name, like this: `[folderName]`. These dynamic parts become `params` that you can use in your layout, page, route, and metadata functions.

Imagine a blog with different posts, each with a unique slug. Your route could look like this: `app/blog/[slug]/page.js`. Here, `[slug]` is the dynamic part for blog posts. The 'slug' becomes a parameter you can use to show the post.

```tsx
// In app/blog/[slug]/page.js
export default async function Post({ params }) {
  return <div>{params.slug}</div>;
}
```

To make dynamic routes load faster, Next.js has a `generateStaticParams` function. It works with dynamic routes to make pages at build time. This means faster page loads because pages are ready to show, without waiting for real-time stuff.

# 🎣 Catch-All Segments

For even more flexible routing, Next.js has 'catch-all' parts. They look like `[...folderName]` with three dots. These parts match lots of things in the URL.

For example, if you're making a shopping site with different categories, you can use a catch-all part: `app/shop/[...categories]/page.js`. This one route can work for URLs like `/shop/clothes`, `/shop/clothes/tops`, `/shop/clothes/tops/t-shirts`, and more.

```tsx
// Inside app/shop/[...categories]/page.js
export default function Category({ params }) {
  // params.categories is an array of categories ['clothes', 'tops', 't-shirts']

  return <div>{params.categories.join(",")}</div>;
}
```

# 🌟 Optional Catch-All Segments

Next.js also supports optional catch-all parts, like `[[...folderName]]`. These parts match the route even without the parameter. So, `app/shop/[[...categories]]/page.js` works for `/shop`, `/shop/clothes`, `/shop/clothes/tops`, and more.

If you're using TypeScript, you can make types for your parameters. This keeps your code safe and stops errors.

Dynamic routing in Next.js is flexible, fast, and easy, making it perfect for lots of routing needs. 🚀🛤️
