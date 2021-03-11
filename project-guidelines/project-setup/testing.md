# Testing

There are many different types of testing, but for frontend, we are mainly interested in the following:

* Static - static type checking combined with linters capture common errors, like typos or incorrect syntax
* Unit tests - focus on critical behavior, business logic and the functionality of your app
* Integration tests - are making sure everything works together correctly
* End-to-end \(e2e\) tests - automated click-testing of critical paths \(instead of relying on your users to do it for you\). Or visual regression testing comparing the implementation of designs.

## Benefits

* Efficient use of developers’ time by not having them test the solution manually
* After every code change, you don’t need to manually retest it \(making it less expensive and less time-consuming, since devs will focus only on development\)
* Easier cooperation between BE and FE \(reduces interactions between platforms after each change\)
* Application stability
* Reduce the number of bugs by a massive number
* Ensure that every functionality works exactly as it is supposed to

## Risks you can incur by not implementing the measure

* Huge waste of money/time that could be used towards feature development
* No one can ensure a “bugless” solution and the proper behavior of all functionalities
* The bigger the solution, the more fragile it becomes
* Really hard or almost impossible to do refactoring

