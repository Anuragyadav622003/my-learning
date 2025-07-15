# 🧭 NestJS Controllers

In NestJS, **controllers** are responsible for handling incoming requests and returning responses to the client. A controller defines a set of routes and methods that map to specific HTTP operations.

---

## 📦 What is a Controller?

- A class annotated with the `@Controller()` decorator.
- Handles **routing** and **request logic**.
- Works closely with **services** for data/business logic.

---

## 🚀 Creating a Controller with CLI

Use the NestJS CLI to generate a new controller:

```bash
nest g controller <name>


```bash
import { Controller, Get, Post, Param, Body } from '@nestjs/common';

@Controller('cats')
export class CatsController {
  
  @Get()
  findAll(): string {
    return 'This action returns all cats';
  }

  @Get(':id')
  findOne(@Param('id') id: string): string {
    return `This action returns a cat with ID: ${id}`;
  }

  @Post()
  create(@Body() createCatDto: any): string {
    return `This action adds a new cat: ${JSON.stringify(createCatDto)}`;
  }
}

