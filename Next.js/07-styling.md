# 🌟 Styling Your Next.js App

## Using CSS Files

You can keep your styles in separate CSS files and import them into your components.

```css
/* styles.css */
.button {
  color: red;
}
```

```javascript
import "styles.css";
```

A common practice is to create a global CSS file and import it into your root Layout.

## CSS Modules

If you want scoped styles, you can use CSS Modules by naming your CSS files with `.module.css`:

```tsx
import styles from "./styles.module.css";

export default function DashboardLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return <section className={styles.dashboard}>{children}</section>;
}
```

```css
/* styles.module.css */
.dashboard {
  padding: 24px;
}
```

## Tailwind CSS

For Tailwind CSS, ensure you update your paths in your Tailwind config:

```javascript
module.exports = {
  content: [
    "./app/**/*.{js,ts,jsx,tsx,mdx}", // Include the `app` directory.
    "./pages/**/*.{js,ts,jsx,tsx,mdx}",
    "./components/**/*.{js,ts,jsx,tsx,mdx}",

    // Or if using the `src` directory:
    "./src/**/*.{js,ts,jsx,tsx,mdx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

Then, import the CSS directives into your global CSS file:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## CSS-in-JS

You can use CSS-in-JS libraries like styled-components. To set up styled-components:

```tsx
import React, { useState } from "react";
import { useServerInsertedHTML } from "next/navigation";
import { ServerStyleSheet, StyleSheetManager } from "styled-components";

export default function StyledComponentsRegistry({
  children,
}: {
  children: React.ReactNode;
}) {
  const [styledComponentsStyleSheet] = useState(() => new ServerStyleSheet());

  useServerInsertedHTML(() => {
    const styles = styledComponentsStyleSheet.getStyleElement();
    styledComponentsStyleSheet.instance.clearTag();
    return <>{styles}</>;
  });

  if (typeof window !== "undefined") return <>{children}</>;

  return (
    <StyleSheetManager sheet={styledComponentsStyleSheet.instance}>
      {children}
    </StyleSheetManager>
  );
}
```

Then, update your layout:

```tsx
import StyledComponentsRegistry from "./registry";

export default function RootLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <html>
      <body>
        <StyledComponentsRegistry>{children}</StyledComponentsRegistry>
      </body>
    </html>
  );
}
```

With these styling options, you can give your Next.js app the look and feel you desire. 🎨✨
