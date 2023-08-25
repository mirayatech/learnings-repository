# 🧭 Simple Routing

Next.js, a framework using React, makes routing easy. It uses files to create routes. The folders in your `/app` directory become parts of the route. You can make nested routes by using nested folders.

For example:

```
/app
  /dashboard
    /settings
      page.js
    /profile
      page.js
```

Each `page.js` file has a React component for a route. Like this:

```tsx
// In /dashboard/settings/page.js
export default function SettingsPage() {
  return <h1>User Settings</h1>;
}
```

If you visit `yourwebsite.com/dashboard/settings`, you'll see "User Settings."

Next.js also has route groups. You put folders in parentheses to group routes. It helps you organize without changing the URL. Like this:

```
/app
  /(admin)
    /dashboard
      /settings
        page.js
      /profile
        page.js
```

Even though `dashboard` is inside `(admin)`, the routes are still `yourwebsite.com/dashboard/settings` and `yourwebsite.com/dashboard/profile`. `(admin)` is just for organization.

Next.js has special files for routes, like `layout.js` for shared layouts, `loading.js` for loading states, and `error.js` for handling errors. They help you make user-friendly experiences.

For advanced routing, Next.js supports parallel routes and route interception. Parallel routes show multiple pages at once, good for dashboards. Route interception lets you use one route inside another.

Next.js 13 introduced server-centric routing. It's fast and works like Single-Page Applications (SPAs).

Next.js routing is flexible, fast, and easy to use. 🚀🛤️
