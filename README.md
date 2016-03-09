# N.W.A Code Guide
A rough guide to coding with the Node With Attitude team
## Code Linting
We are using **[Standard](https://github.com/feross/standard)** with the [standard-react plugin](https://github.com/feross/eslint-config-standard-react) for JSX/React.

Install the relevant [plugin](https://github.com/feross/standard#text-editor-plugins) for your IDE and point your IDE at the .eslintrc file, and just type away correcting what needs to be corrected.

**Major points:** No semicolons. 2 space indentation. Spaces after everything. No unused vars. use `===` except for `==` null to check for `null || undefined`

**But what are the rules!?!** No one read rules. Let your linter tell you the rules, you'll remember it better this way. Google or ask if you are unsure of the meaning.

**Autofix:** Run `npm run lint:fix`  to autofix stuff. And then turn on auto linting in your ide. 

**Help:**  
You can temporarily disable linting using standard `/* eslint-disable no-use-before-define */` at the top of file.

 If you need globals for some reason, use `/* global myVar1, myVar2 */`

## Test Coverage
We are aiming for 90% test coverage. If you believe no test is needed, create a name.spec.js file and create a test that just returns true with a note that says 'test is unneeded. Have this confirmed by a teammate. 
**Do not** use when you haven't gotten around to creating the test yet, if you haven't had time then leave the test file missing.

**Naming:** Every .js file should have a test named `name-of-file.spec.js` in the same fame folder as the js file.

**TDD:** Test can be written before or after. Whatever works for you.

## Pull Requests / Git Flow
We are using Git Flow. All changes should be in a branch. All changes should be code reviewed and approved. All code should have been reviewed. A comment made and pass automated unit testing. 
* **Before release** end-to-end tests not required.
* **Minor changes** don't require end-to-end tests. 
* **Major changes** should be run through end-to-end.

## Code Style
Mostly just follow [Airbnb React/JSX Style guide](https://github.com/airbnb/javascript/tree/master/react)

#### Key points
**Most important `function`'s first:** Functions are hoisted. Put the most important stuff at the top if the file. And the least important lower down. Even if you use a function before it's been declared.

**Initialise `const` & `let` where needed:** Don't pre-create any of your `const` and `let` declarations. Declare at the same time as needed.

**export functions in place:** use `export function () {}` rather than exporting your functions at the end. This allows you to know if its exported when reading it.

**Use ES6 Class over React.createClass:** Use the ES6 standard `class *name* extends React.Component {}` instead of `React.createClass` means using a standard and createClass may be removed in the future.

**Always bind your component methods:** A react component made with a class wont auto bind. Therefore always bind any method in a react component, even if it isn't needed.

**Always use `() => { return }`:** Always use the `() => {}` method even when it isn't needed for clarity you are creating a function. 
* Prefer `(number) => { return 2 * number}` over `number => 2 * number`

**What about currying?:** For currying you can use the shorter version without a *return* or *{}*. e.g.
* `export default (defaultstore) => (next) => (action) => { return next(action) }`

**Prefer descriptive function names:** It is better to use a very long function name that describes what something is doing, than a short one that is harder to understand what is going on. e.g. 
* Prefer `StringOfNumbersToArrayOfInts` over `makeInts`

**Not covered here or AirBnB:** If it's not covered. Then think about adding it here, or just do whatever. It probably isn't important enough to worry about.

## Living document
This is a **living document**. Feel free to suggest changes or make them yourself.
