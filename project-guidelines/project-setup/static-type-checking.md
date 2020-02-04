# Static type checking

Languages [TypeScript](https://www.typescriptlang.org/) or [Flow](https://flow.org/) are very suitable for frontend development.

- Fewer bugs in run-time, because bugs are caught in compile-time
- Highly productive developer experience
- Better onboarding of new developers
- Easier to refactor and debug

## TypeScript

TypeScript is very popular these days. It’s developed by Microsoft, Angular from version 2 is completely written in it, backend developers love it and it’s become a more common language for libraries.

TypeScript is not, in fact, a programming language. It’s a typed superset of JavaScript. This means that any JavaScript is a TypeScript, and TypeScript adds extra features into JavaScript \(besides types, ES6 syntax and JSX support\). TypeScript is compiled into plain JavaScript.

### Benefits

- Common and with a high adoption rate within a large community
- Developed by Microsoft
- Great tooling and integration in code editors or IDEs
- A lot of typings for 3rd party libraries available

### Risks

- A bit of a harder learning curve, especially for junior developers
- Potentially hard configuration \(you must know what are you doing\)
- The official documentation is not up to date
- Before `babel7`, compiler must be used with TypeScript \(tsc\); this makes adoption and upgrading to TypeScript complex
- Requires a build step, which sometimes isn’t suitable—or the overhead just isn’t worth it

## Flow

Flow is developed by Facebook and used to be much more suitable for React than TypeScript. Flow had better support for React from the very beginning. Integration to an existing project was much easier and more straightforward than TypeScript. But these days, Flow is losing its popularity.

### Benefits

- Feels more like JavaScript
- You can simply add types to a file by adding @flow annotation at the beginning of a file

### Risks

- TypeScript is more performant and stable
- A lot of memory issues and editor integration problems
- People behind Flow are more focused on ReasonML last days

## ReasonML

ReasonML is a JavaScript-like syntax for OCaml that can be compiled into JavaScript. It’s quite new but looks very promising.

### Benefits

- Super fast and stable
- Fully typed and functional language
- Can compile to any platform supported by OCaml or JavaScript

### Risks

- Small community compared to JavaScript or TypeScript
- Difficult learning path
- Usually not preferred by clients because there aren’t enough developers
