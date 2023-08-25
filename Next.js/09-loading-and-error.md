# 🔄 Handling Loading and Errors

## Loading State

In Next.js, we can make loading feel snappy. When a page or layout is fetching data, we can show an instant loading state. Here's how:

- 🚀 Create a component in the same directory as the page or layout that's fetching data.
- 📦 Name it `loading.js`.

For example:

```tsx
/app
	/dashboard
	  page.tsx
    loading.tsx
```

And in `loading.tsx`:

```tsx
const Loader = () => <div>Loading...</div>;

export default Loader;
```

This way, you give users something to look at while your data loads. 🏋️‍♂️

## Error State

Now, let's handle errors gracefully. When a page or layout encounters an error during rendering, we can display a helpful message by creating an `error.js` file.
