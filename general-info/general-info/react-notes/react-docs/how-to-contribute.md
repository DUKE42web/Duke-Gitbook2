# How to Contribute

React is one of Facebook's first open source projects that is both under very active development and is also being used to ship code to everybody on [facebook.com](https://www.facebook.com). We're still working out the kinks to make contributing to this project as easy and transparent as possible, but we're not quite there yet. Hopefully this document makes the process for contributing clear and answers some questions that you may have.

#### [Code of Conduct](https://github.com/facebook/react/blob/main/CODE_OF_CONDUCT.md) <a href="#code-of-conduct" id="code-of-conduct"></a>

Facebook has adopted the [Contributor Covenant](https://www.contributor-covenant.org) as its Code of Conduct, and we expect project participants to adhere to it. Please read [the full text](https://github.com/facebook/react/blob/main/CODE_OF_CONDUCT.md) so that you can understand what actions will and will not be tolerated.

#### Open Development <a href="#open-development" id="open-development"></a>

All work on React happens directly on [GitHub](https://github.com/facebook/react). Both core team members and external contributors send pull requests which go through the same review process.

#### Semantic Versioning <a href="#semantic-versioning" id="semantic-versioning"></a>

React follows [semantic versioning](https://semver.org). We release patch versions for critical bugfixes, minor versions for new features or non-essential changes, and major versions for any breaking changes. When we make breaking changes, we also introduce deprecation warnings in a minor version so that our users learn about the upcoming changes and migrate their code in advance. Learn more about our commitment to stability and incremental migration in our versioning policy.

Every significant change is documented in the [changelog file](https://github.com/facebook/react/blob/main/CHANGELOG.md).

#### Branch Organization <a href="#branch-organization" id="branch-organization"></a>

Submit all changes directly to the [`main branch`](https://github.com/facebook/react/tree/main). We don't use separate branches for development or for upcoming releases. We do our best to keep `main` in good shape, with all tests passing.

Code that lands in `main` must be compatible with the latest stable release. It may contain additional features, but no breaking changes. We should be able to release a new minor version from the tip of `main` at any time.

#### Feature Flags <a href="#feature-flags" id="feature-flags"></a>

To keep the `main` branch in a releasable state, breaking changes and experimental features must be gated behind a feature flag.

Feature flags are defined in [`packages/shared/ReactFeatureFlags.js`](https://github.com/facebook/react/blob/main/packages/shared/ReactFeatureFlags.js). Some builds of React may enable different sets of feature flags; for example, the React Native build may be configured differently than React DOM. These flags are found in [`packages/shared/forks`](https://github.com/facebook/react/tree/main/packages/shared/forks). Feature flags are statically typed by Flow, so you can run `yarn flow` to confirm that you've updated all the necessary files.

React's build system will strip out disabled feature branches before publishing. A continuous integration job runs on every commit to check for changes in bundle size. You can use the change in size as a signal that a feature was gated correctly.

#### Bugs <a href="#bugs" id="bugs"></a>

**Where to Find Known Issues**

We are using [GitHub Issues](https://github.com/facebook/react/issues) for our public bugs. We keep a close eye on this and try to make it clear when we have an internal fix in progress. Before filing a new task, try to make sure your problem doesn't already exist.

**Reporting New Issues**

The best way to get your bug fixed is to provide a reduced test case. This [JSFiddle template](https://jsfiddle.net/Luktwrdm/) is a great starting point.

**Security Bugs**

Facebook has a [bounty program](https://www.facebook.com/whitehat/) for the safe disclosure of security bugs. With that in mind, please do not file public issues; go through the process outlined on that page.

#### How to Get in Touch <a href="#how-to-get-in-touch" id="how-to-get-in-touch"></a>

- IRC: [#reactjs on freenode](https://webchat.freenode.net/?channels=reactjs)
- Discussion forums

There is also [an active community of React users on the Discord chat platform](https://www.reactiflux.com) in case you need help with React.

#### Proposing a Change <a href="#proposing-a-change" id="proposing-a-change"></a>

If you intend to change the public API, or make any non-trivial changes to the implementation, we recommend [filing an issue](https://github.com/facebook/react/issues/new). This lets us reach an agreement on your proposal before you put significant effort into it.

If you're only fixing a bug, it's fine to submit a pull request right away but we still recommend to file an issue detailing what you're fixing. This is helpful in case we don't accept that specific fix but want to keep track of the issue.

#### Your First Pull Request <a href="#your-first-pull-request" id="your-first-pull-request"></a>

Working on your first Pull Request? You can learn how from this free video series:

[**How to Contribute to an Open Source Project on GitHub**](https://app.egghead.io/courses/how-to-contribute-to-an-open-source-project-on-github)

To help you get your feet wet and get you familiar with our contribution process, we have a list of [**good first issues**](https://github.com/facebook/react/issues?q=is:open+is:issue+label:%22good+first+issue%22) that contain bugs that have a relatively limited scope. This is a great place to get started.

If you decide to fix an issue, please be sure to check the comment thread in case somebody is already working on a fix. If nobody is working on it at the moment, please leave a comment stating that you intend to work on it so other people don't accidentally duplicate your effort.

If somebody claims an issue but doesn't follow up for more than two weeks, it's fine to take it over but you should still leave a comment.

#### Sending a Pull Request <a href="#sending-a-pull-request" id="sending-a-pull-request"></a>

The core team is monitoring for pull requests. We will review your pull request and either merge it, request changes to it, or close it with an explanation. For API changes we may need to fix our internal uses at Facebook.com, which could cause some delay. We'll do our best to provide updates and feedback throughout the process.

**Before submitting a pull request,** please make sure the following is done:

1. Fork [the repository](https://github.com/facebook/react) and create your branch from `main`.
2. Run `yarn` in the repository root.
3. If you've fixed a bug or added code that should be tested, add tests!
4. Ensure the test suite passes (`yarn test`). Tip: `yarn test --watch TestName` is helpful in development.
5. Run `yarn test --prod` to test in the production environment.
6. If you need a debugger, run `yarn debug-test --watch TestName`, open `chrome://inspect`, and press "Inspect".
7. Format your code with [prettier](https://github.com/prettier/prettier) (`yarn prettier`).
8. Make sure your code lints (`yarn lint`). Tip: `yarn linc` to only check changed files.
9. Run the [Flow](https://flowtype.org) typechecks (`yarn flow`).
10. If you haven't already, complete the CLA.

#### Contributor License Agreement (CLA) <a href="#contributor-license-agreement-cla" id="contributor-license-agreement-cla"></a>

In order to accept your pull request, we need you to submit a CLA. You only need to do this once, so if you've done this for another Facebook open source project, you're good to go. If you are submitting a pull request for the first time, just let us know that you have completed the CLA and we can cross-check with your GitHub username.

[**Complete your CLA here.**](https://code.facebook.com/cla)

#### Contribution Prerequisites <a href="#contribution-prerequisites" id="contribution-prerequisites"></a>

- You have [Node](https://nodejs.org) installed at v8.0.0+ and [Yarn](https://yarnpkg.com/en/) at v1.2.0+.
- You have [JDK](https://www.oracle.com/technetwork/java/javase/downloads/index.html) installed.
- You have `gcc` installed or are comfortable installing a compiler if needed. Some of our dependencies may require a compilation step. On OS X, the Xcode Command Line Tools will cover this. On Ubuntu, `apt-get install build-essential` will install the required packages. Similar commands should work on other Linux distros. Windows will require some additional steps, see the [`node-gyp` installation instructions](https://github.com/nodejs/node-gyp#installation) for details.
- You are familiar with Git.

#### Development Workflow <a href="#development-workflow" id="development-workflow"></a>

After cloning React, run `yarn` to fetch its dependencies. Then, you can run several commands:

- `yarn lint` checks the code style.
- `yarn linc` is like `yarn lint` but faster because it only checks files that differ in your branch.
- `yarn test` runs the complete test suite.
- `yarn test --watch` runs an interactive test watcher.
- `yarn test --prod` runs tests in the production environment.
- `yarn test <pattern>` runs tests with matching filenames.
- `yarn debug-test` is just like `yarn test` but with a debugger. Open `chrome://inspect` and press "Inspect".
- `yarn flow` runs the [Flow](https://flowtype.org) typechecks.
- `yarn build` creates a `build` folder with all the packages.
- `yarn build react/index,react-dom/index --type=UMD` creates UMD builds of just React and ReactDOM.

We recommend running `yarn test` (or its variations above) to make sure you don't introduce any regressions as you work on your change. However, it can be handy to try your build of React in a real project.

First, run `yarn build`. This will produce pre-built bundles in `build` folder, as well as prepare npm packages inside `build/packages`.

The easiest way to try your changes is to run `yarn build react/index,react-dom/index --type=UMD` and then open `fixtures/packaging/babel-standalone/dev.html`. This file already uses `react.development.js` from the `build` folder so it will pick up your changes.

If you want to try your changes in your existing React project, you may copy `build/node_modules/react/umd/react.development.js`, `build/node_modules/react-dom/umd/react-dom.development.js`, or any other build products into your app and use them instead of the stable version.

If your project uses React from npm, you may delete `react` and `react-dom` in its dependencies and use `yarn link` to point them to your local `build` folder. Note that **instead of `--type=UMD` you'll want to pass `--type=NODE` when building**. You'll also need to build the `scheduler` package:

```
cd ~/path_to_your_react_clone/
yarn build react/index,react/jsx,react-dom/index,scheduler --type=NODE

cd build/node_modules/react
yarn link
cd build/node_modules/react-dom
yarn link

cd ~/path/to/your/project
yarn link react react-dom
```

Every time you run `yarn build` in the React folder, the updated versions will appear in your project's `node_modules`. You can then rebuild your project to try your changes.

If some package is still missing (e.g. maybe you use `react-dom/server` in your project), you can always do a full build with `yarn build`. Note that running `yarn build` without options takes a long time.

We still require that your pull request contains unit tests for any new functionality. This way we can ensure that we don't break your code in the future.

#### Style Guide <a href="#style-guide" id="style-guide"></a>

We use an automatic code formatter called [Prettier](https://prettier.io). Run `yarn prettier` after making any changes to the code.

Then, our linter will catch most issues that may exist in your code. You can check the status of your code styling by simply running `yarn linc`.

However, there are still some styles that the linter cannot pick up. If you are unsure about something, looking at [Airbnb's Style Guide](https://github.com/airbnb/javascript) will guide you in the right direction.

#### Request for Comments (RFC) <a href="#request-for-comments-rfc" id="request-for-comments-rfc"></a>

Many changes, including bug fixes and documentation improvements can be implemented and reviewed via the normal GitHub pull request workflow.

Some changes though are "substantial", and we ask that these be put through a bit of a design process and produce a consensus among the React core team.

The "RFC" (request for comments) process is intended to provide a consistent and controlled path for new features to enter the project. You can contribute by visiting the [rfcs repository](https://github.com/reactjs/rfcs).

#### License <a href="#license" id="license"></a>

By contributing to React, you agree that your contributions will be licensed under its MIT license.

#### What Next? <a href="#what-next" id="what-next"></a>

Read the next section to learn how the codebase is organized.
