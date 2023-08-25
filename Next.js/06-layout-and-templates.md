# 🌟 Layouts and Templates

## Layouts

Layouts are like the frames around a picture. They wrap your pages and help create a consistent look across different parts of your website. Think of them as the containers for your content.

- 🔄 Layouts are components that you can use across multiple pages.
- 🌐 They wrap around your page content, like a navigation bar.
- 🖼️ Layouts are only rendered once, so they don't change when you switch pages.
- ✏️ To create a layout, it's similar to creating a page, but you make a `layout.js` instead of a `page.js`.
- 🏞️ For example, you can have a `RootLayout` that contains navigation.

```tsx
/app
	page.tsx
	layout.tsx
  /about
    page.tsx
```

```tsx
const RootLayout = ({ children }) => {
  return (
    <div>
      <Nav />
      <div>{children}</div>
    </div>
  );
};

export default RootLayout;
```

- 🌳 You must have a root layout in your app, but you can have more advanced layouts when you use grouping and nesting.
- 🌿 Just like pages, layouts can fetch data if needed.

## Templates

Templates are a lot like layouts, but with a twist!

- 🔄 Templates also wrap your pages, just like layouts.
- 🔃 However, templates **do** get rendered every time you switch pages.
- 🌟 This makes them great for things like fancy animations or code that should run each time a page loads.

Templates and layouts are both useful tools for building a cohesive and dynamic web experience. 🚀🎨
