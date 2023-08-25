# ⚙️ Server Actions Made Simple

Server actions are a handy way to run server-side code without the hassle of setting up a new API route. They can even work when JavaScript is disabled in the browser. Here's how you create one:

```tsx
const Home = async () => {
  const update = async (data) => {
    "use server";
    const email = data.get("email");
    // ....
  };

  return (
    <form action={update}>
      <input name="email" type="email" />
      <button type="submit">sign up</button>
    </form>
  );
};
```

- 🛠️ A Server Action is a function created with the `use server` directive. You can place this directive either in the function body as shown or at the top of a file.
- 💡 You can do all sorts of things in a server action, but you can't wait for a response. They're perfect for tasks where the client doesn't need an immediate response.

If you need to make changes to data and have it reflected on the screen, you can use `revalidate` to tell Next.js to fetch the data again for that path:

```tsx
const newTodo = async (data) => {
  "use server";

  const todo = data.get("todo");
  await db.todo.create({
    /*....*/
  });
  revalidate("/todos"); // fetch data again on the /todos page
};
```

You can use server actions in various ways, but for now, it's recommended to use them mainly for forms that trigger non-mutative actions on the server. 🚀🔧
