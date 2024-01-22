<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="200" alt="Nest Logo" /></a>
</p>

# REST API WITH NEST

How to Create a REST API with NestJS

Using Typescript, Postgres, TypeORM and Docker

If you’re curious or want to learn how NestJS works, then in this tutorial I’ll go step-by-step through the fundamental aspects of Nest and help you take the first step.

We are going to develop a REST API project with CRUD operations in Typescript using PostgreSQL, TypeORM and Docker.

## Getting Started

1. Clone this repository
```
git clone git@github.com:Gapur/nest-academy-rest-api.git
```
2. Install dependencies
```
npm install
```
3. Launch app
```
npm run start # for npm
```

## What is NestJS?
Before we begin, we need to know what NestJS is. Nest (NestJS) is a framework for building efficient, scalable Node.js server-side apps in JavaScript and Typescript. Either way, under the hood Nest uses Express by default, or we can configure Fastify.

Nest has a special modular architecture than other JavaScript frameworks. It was inspired by Angular. For example, everything related to working with users will be grouped into one module for users. This way, as our project grows, it will be easier to maintain, scale, support and test. This is a very big plus for NestJS.
The NestJS architecture contains three main concepts:
- Controllers — responsible for handling incoming requests and returning responses to the client
- Providers — a fundamental concept in Nest where controllers delegate more complex tasks to them. Many of Nest’s base classes can be thought of as providers — services, repositories, factories, helpers, etc.
- Modules — provide metadata that Nest uses to organize the structure of the app

## Setting Up the Project

First, we’ll create a new `Nest` project where we’ll create, get, update, and delete students using the REST API. We can create a new project with two options:
 - NestJS CLI
 - clone a starter project

Let’s create our project using the NestJS CLI. If you are not familiar, it is a command-line interface tool that helps you initialize, develop, and maintain your Nest apps. If you don’t have NestJS CLI, you can install it using the following command:

```sh
npm i -g @nestjs/cli
```

Now it is ready and installed globally so we can use it anywhere. Let’s create a new Nest project through the following lines of code:

```
nest new nest-academy-rest-api
```

Great, we’ve successfully created our Nest app.

If we go to the src/ folder, there will be several main files:
 - app.controller.ts — a basic controller with a single route
 - app.controller.spec.ts — the unit tests for the controller
 - app.module.ts — the root module of the app
 - app.service.ts — a basic service with a single method
 - main.ts — the entry file of the app

The `main.ts` file includes an async function that will bootstrap our app:

```ts
import { NestFactory } from '@nestjs/core';

import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule); // create Nest app
  await app.listen(3000); // listen on port 3000
}

bootstrap(); // run the app
```

Above, we created an instance of the Nest app and run it on port 3000 using the static creation method of NestFactory.

One last thing before we start coding, let’s check if everything works by running the app using the following command:
```
npm start
```
