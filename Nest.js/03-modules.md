# Core Module 🧱

- Decorators are like labels that tell Nest.js about the role of a class.
- `AppModule` is where you define the backbone of your app.

```typescript
import { Module } from "@nestjs/common";
import { AppController } from "./app.controller";
import { AppService } from "./app.service";

@Module({
  imports: [],
  controllers: [AppController],
  providers: [AppService],
})
export class AppModule {}
```

Filename: `05-prerequisites.md`

# Prerequisites 📚

- **Postman**: A tool for API development that helps you build and test APIs quickly.
- **Insomnia**: A client for working with REST and GraphQL APIs, available on many platforms.

---

Filename: `06-cli-commands.md`

# CLI Commands ⌨️

- `nest g co`: Command to create a new controller.
- `nest g s`: Command to create a new service.
- If you don't want a test file, add `--no-spec` to your command.
- `nest g class coffees/dto/create-coffee.dto --no-spec`: Command to create a new DTO class without a test file.

---

Filename: `07-dto.md`

# Data Transfer Object (DTO) 📦

- DTOs are used to shape and send data from one part of your app to another.

---

Filename: `08-validation.md`

# Input Validation 🛡️

- Nest.js has a validation pipe that checks the data coming into your app to make sure it's right.

---

Each file provides a focused overview of a particular concept or feature in Nest.js, using plain language and emojis to make the documentation friendlier and easier to digest. I've now included all the sections from your provided text. If there are any more details or sections to be included or further adjustments needed, please let me know!
