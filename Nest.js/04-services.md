# Services 🛠️

- Services are where the business logic and data storage tasks happen.
- Keeping logic in services makes our code cleaner and more maintainable.
- Services are providers, which means they are used to inject functionality into other parts of the app.

```typescript
import { Injectable } from "@nestjs/common";

@Injectable()
export class AppService {
  getHello(): string {
    return "Hello World!";
  }
}
```
