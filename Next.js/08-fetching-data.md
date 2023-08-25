# 🌐 Fetching Data Made Simple

## Server Components

Server components are your data-fetching heroes. They work on the server and are more like regular JavaScript functions. So, no fancy client-side JavaScript logic here!

- 🚀 You can easily fetch data with a simple `async/await` in a server component.
- ✨ Here's an example:

```tsx
const getContent = async () => {
  const res = await fetch("https://cms.com/......");
  const content = await res.json();
  return content.homePage;
};

const HomePage = async () => {
  const content = await getContent();
  return <div>{content.title}</div>;
};

export default HomePage;
```

- 🏗️ This whole component runs on the server every time someone visits the matching route.
- 🌐 You can use `fetch` in your server-side calls, and it's built into Next.js.
- 🏎️ Plus, it comes with advanced caching and deduping to keep things speedy.

## Client Components

For now, you can stick with your usual data-fetching methods on the client side. No need to change anything there! 🛒🌟
