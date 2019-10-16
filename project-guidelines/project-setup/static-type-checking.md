# Static type checking

Languages [TypeScript](https://www.typescriptlang.org/) or [Flow](https://flow.org/) are nicely suitable for frontend development.

* Fewer bugs in run-time, because bugs are caught in compile-time
* Highly productive developer experience
* Better onboarding of new developers
* Easier to debug

## TypeScript

TypeScript is very popular these days. It’s developed by Microsoft, Angular from version 2 is completely written in it, backend developer loves it and it’s become a more common language for libraries.

TypeScript is not, in fact, a programming language, but it is a typed superset of JavaScript. This means that any JavaScript is a TypeScript and TypeScript adds extra features into JavaScript \(besides types, ES6 syntax or JSX support\). TypeScript is compiled into plain JavaScript.

### Benefits

* Well spread and adoption within a large community
* Developed by Microsoft
* Great tooling and integration in code editors or IDEs
* A lot of typings for 3rd party libraries available

### Risks

* A bit harder learning curve, especially for junior developers
* Potentially hard configuration \(you must know what are you doing\)
* The official documentation is not up to date
* Before babel7 there must be used with TypeScript \(tsc\) compiler, which brings a lot of complexity in adoption and makes it difficult to upgrade to TypeScript.
* It requires a build step, which sometimes couldn’t be suitable, or the overhead is just not worth it

## Flow

Flow is developed by Facebook and it used to be much more suitable for React than TypeScript. Flow had better support for React from the very beginning. Integration to a existing project was much easier and straightforward than TypeScript. But these days Flow is losing its popularity.

### Benefits

* Feels more like JavaScript
* You can simply add types to a file by adding @flow annotation at the beginning of a file

### Risks

* TypeScript is more performant and stable
* A lot of memory issues and editor integration problems
* People behind Flow are more focused on ReasonML last days

## ReasonML

ReasonML is JavaScript like syntax for OCaml that can be compiled into JavaScript. It’s quite new but looks very promising.

### Benefits

* Super fast and stable
* Fully typed and functional language
* Can compile to any platform supported by OCaml or JavaScript

### Risks

* Small community compared to JavaScript or TypeScript
* Difficult learning path
* Usually not wanted by clients, because there are not enough developers

