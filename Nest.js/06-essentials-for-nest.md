# Development Essentials for Nest.js 🛠️

## Prerequisites 📚

- Postman: A tool for API development that helps you build and test APIs quickly.
- Insomnia: A client for working with REST and GraphQL APIs, available on many platforms.

## CLI Commands ⌨️

- `nest g co`: Create a new controller. Controllers direct traffic, handling incoming requests and responses.
- `nest g s`: Spin up a new service. Services are the workhorses, managing business logic and data.
- `--no-spec`: Use this flag to skip creating test files if you want to keep things simple.

Alright, let's add some explanatory text and code examples for the DTO and Input Validation sections in Nest.js, and we’ll put it all in one file named `08-cli-dto-validation.md`.

## CLI Commands ⌨️

- `nest g co`: Create a new controller. Controllers direct traffic, handling incoming requests and responses.
- `nest g s`: Spin up a new service. Services are the workhorses, managing business logic and data.
- `--no-spec`: Use this flag to skip creating test files if you want to keep things simple.

## Data Transfer Object (DTO) 📦

DTOs in Nest.js help you define the structure of data for operations like creating or updating an item. They're like blueprints that every piece of data has to match to be considered valid in your app. Here's an example of a DTO for creating a coffee item:

```typescript
import { IsString, IsInt } from "class-validator";

export class CreateCoffeeDto {
  @IsString()
  readonly name: string;

  @IsString()
  readonly brand: string;

  @IsInt()
  readonly recommendations: number;
}
```

In this `CreateCoffeeDto`, we're expecting `name` and `brand` to be strings and `recommendations` to be an integer. The `class-validator` package is used here, which integrates seamlessly with Nest.js, allowing you to use decorators to apply validation rules.

## Input Validation 🛡️

Nest.js's validation pipe works with DTOs to ensure the data fits the blueprint before it's processed by your application. This means you can catch errors early and provide feedback. Here's how you can apply the validation pipe globally:

```typescript
import { NestFactory } from "@nestjs/core";
import { AppModule } from "./app.module";
import { ValidationPipe } from "@nestjs/common";

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  app.useGlobalPipes(new ValidationPipe());
  await app.listen(3000);
}
bootstrap();
```

By adding `new ValidationPipe()` in the `bootstrap` function, every incoming client request is validated against the DTOs defined in your controllers. If a client sends data that doesn't match the DTO structure, the Nest.js server will respond with an error before your route handler is ever reached.
