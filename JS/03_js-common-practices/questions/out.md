# Exam questions

<details>
<summary>1. What are advantages of JEST testing framework?</summary>

>#### Answer:
>The biggest advantage of using Jest is that it works out of the box with minimal setup or configuration. Much of this is because it comes with an assertion library and mocking support. The tests are written in BDD style, similar to any other modern testing library. You can literally just put your tests inside of a directory called __tests__ or name them with a .spec.js or .test.js extension, then run jest and it works. That is pretty sweet.
Jest also supports snapshot testing, which can be really handy for preventing accidental UI regressions when doing React development. These tests record snapshots of rendered component structure and compare them to future renderings. When they don’t match, your test fails, indicating that something has changed. You can easily tell Jest to update the snapshot if this change is expected (e.g. for a newly added feature).
</details>

<details>
<summary>2. What is Enzyme testing framework?</summary>

>#### Answer:
>Enzyme is a JavaScript Testing utility for React that makes it easier to test your React Components' output. You can also manipulate, traverse, and in some ways simulate runtime given the output.
Enzyme's API is meant to be intuitive and flexible by mimicking jQuery's API for DOM manipulation and traversal.
</details>

<details>
<summary>3. What is the difference between --save and -save-dev?</summary>

>#### Answer:
>``--save-dev`` is used to save a package for development. Example: unit tests, minimization.
>``--save`` is used to save the package needed to run applications.
</details>

<details>
<summary>4. What is the difference between a tilde (~) and a carriage (^) in a .json package?</summary>

>#### Answer:
>The tilde is the latest minor version (average). ~ 1.2.3 will correspond to all versions 1.2.x, but 1.3.0 will be missing.
>
>The carriage, on the other hand, is more relaxed. It will update you to the latest major version (first number). ^ 1.2.3 will correspond to any release 1.xx, including 1.3.0, but will be held at 2.0.0.
</details>

<details>
<summary>5. How to remove npm modules in js node?</summary>

>#### Answer:
>The command is just ``npm uninstall <name>``
>
>The nodejs documents https://npmjs.org/doc/ contain all the commands you need to know using npm.
>
>The local installation will be in your application's ``node_modules/``. This will not affect the application if the module remains there without reference to it.
>
>However, if you delete a global package, all applications that reference it will crash.
>
>Here are the different options:
>
>``npm uninstall <name>`` removes the module from ``node_modules``, but not ``package.json``
>
>``npm uninstall <name> --save`` also removes it from ``dependencies`` in ``package.json``
>
>``npm uninstall <name> --save-dev`` also removes it from ``devDependencies`` in ``package.json``
>
>``npm -g uninstall <name> --save`` also removes it globally
</details>

<details>
<summary>6. How to disable eslint rules for available strings</summary>

>#### Answer:
>``/* eslint-disable no-alert, no-console, eslint-disable-line */``
>Docs link:  http://eslint.org/docs/user-guide/configuring.html#configuring-rules
```js
    /* eslint-disable */

    alert('foo');

    /* eslint-enable */
```
</details>
<details>
<summary>7. Write a simple unit-test</summary>

>#### Answer:
>**Need to add answer**
</details>

<details>
<summary>8. Tell about the basic concepts of the webpack:

* Entry
* Output
* Loaders
* Plugins
* Mode
* Browser Compatibility
</summary>

>#### Answer:
>#### Entry
>An entry point indicates which module webpack should use to begin building out its internal dependency graph. webpack will figure out which other modules and libraries that entry point depends on (directly and indirectly).
>#### Output:
>The output property tells webpack where to emit the bundles it creates and how to name these files. It defaults to ./dist/main.js for the main output file and to the ./dist folder for any other generated file.
>#### Loaders:
>Out of the box, webpack only understands JavaScript and JSON files. Loaders allow webpack to process other types of files and convert them into valid modules that can be consumed by your application and added to the dependency graph.
>#### Plugins:
>While loaders are used to transform certain types of modules, plugins can be leveraged to perform a wider range of tasks like bundle optimization, asset management and injection of environment variables.
>#### Mode:
>By setting the mode parameter to either development, production or none, you can enable webpack's built-in optimizations that correspond to each environment.
>#### Browser Compatibility:
>webpack supports all browsers that are ES5-compliant (IE8 and below are not supported). webpack needs Promise for import() and require.ensure(). If you want to support older browsers, you will need to load a polyfill before using these expressions.

</details>

