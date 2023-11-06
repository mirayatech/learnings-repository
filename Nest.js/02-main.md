# Starting Your App 🚀

- We get our Nest.js app running on port 3000 here.
- The `main.ts` file is where it all begins.
- `AppModule` is the main building block of your app.

```typescript
import { NestFactory } from "@nestjs/core";
import { AppModule } from "./app.module";

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  await app.listen(3000);
}
bootstrap();
```
