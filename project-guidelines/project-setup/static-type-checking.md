# Static type checking

For static type checking, we use [TypeScript](https://www.typescriptlang.org/). Typescript is a strongly-typed superset of JavaScript, which means that any valid JavaScript code is a valid TypeScript code, but on top of it we get additional features, such as type checking, ES6 syntax and JSX support. TypeScript is compiled into plain JavaScript.

Static type checking is very important as it means:

- More robust code
- Having fewer bugs in run-time, because bugs are caught in compile-time
- Highly productive developer experience
- Better onboarding of new developers
- Easy debugging and refactoring

### Benefits of TypeScript

- Common and with a high adoption rate within a large community
- Developed and maintained at Microsoft by very experienced developers
- Has great tooling and integration in code editors or IDEs
- Almost any 3rd party library has TS typings, available either as part of the library, or as a standalone @types/\* package

It should be noted, that TypeScript doesn't guarantee 100% type safety. Since most of types are defined by users, a mistake in a type definition might lead to mistakes in code, so we should be careful when defining our types.
