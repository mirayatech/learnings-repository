## Introduction to Next.js ⚡️

Welcome to the Next.js Basics section in my learning repository!

### What is Next.js? 🤔

Next.js is a powerful React framework that simplifies the process of building fast, server-rendered web applications. It provides a great developer experience with features like automatic code splitting, server-side rendering, and easy routing.

_Note: Next.js is an open-source project with a strong community and is widely used in production by companies of all sizes._

## Key Concepts in Next.js 13 🗝️

Next.js 13 introduced several major features and improvements:

#### App Directory (Beta)

The app directory provides a new way to structure Next.js applications that is easier, faster, and ships less client JavaScript:

- **Server Components**: Makes server-first the default for dynamic applications. Server components render on the server and return compiled JSX, reducing the amount of JavaScript sent to the client and enabling faster page loads.

- **Layouts**: Allows sharing UI between routes while preserving state. Layouts can be used to fetch data needed across multiple pages.

- **Streaming**: Displays instant loading states and streams in UI as it renders.

- **Data Fetching**: The `fetch` API enables component-level data fetching.

#### Turbopack (Alpha)

Turbopack is a Rust-based bundler that provides:

- 700x faster updates than Webpack
- 10x faster updates than Vite
- 4x faster cold starts

#### next/image

The new Image component in Next.js 13 provides:

- Less client-side JavaScript
- Easier styling
- Requires alt tags by default
- Faster with native browser lazy loading

#### @next/font (Beta)

The new font system provides:

- Automatic self-hosted fonts
- Removes external network requests
- Zero layout shift using `size-adjust`

In summary, the key concepts in Next.js 13 are:

- Server Components (RSC)
- Layouts
- Turbopack - the Rust-based bundler
- Improved `next/image` and `@next/font` components
- The new app directory routing system

### Further Resources 📚

- [Next.js Documentation](https://nextjs.org/)
- [Introduction to Next.js 13+, v3 by Scott Moss](https://frontendmasters.com/courses/next-js-v3/)
