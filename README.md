# Element Framework (EF) V5

Element Framework is Refinitiv design system components that provides components and tooling with Refinitiv's design system to help product teams work faster and more efficiently.

## Elements Monorepo

This is the monorepo for Element Framework elements, its supporting modules and tools.

* `packages` - All packages.
* `packages/elements` - Elements package.

### Setup development environment

Install npm@7 CLI:

```bash
npm install -g npm
```

Initialize project:

```bash
git clone git@git.sami.int.thomsonreuters.com:elf/refinitiv-ui.git
cd refinitiv-ui
npm install
```

Build all packages:

```bash
npm run build
```

### CLI Commands

The command-line interface tool that you can use to demo, develop, test, and maintain this repository

Run demo page of individual element:

``` bach
cd packages/elements
npm start button
```

or

``` bach
npm start button -w=@refinitiv-ui/elements
```

For simplicity, some commands reflected at the root level as well:

```bash
npm start button
```

#### Elements Package Command Overview

| Command | Target | Description | Example |
| --- |:--- | --- | --- |
| npm start | `<target>`&#160;(required) | Build and serves a package or element which demoable. | npm start button |
| npm run test  | `<target>` | Runs unit tests in a package or element. If not define the `<target>`, it will runs unit test in all packages. | npm run test button |
| npm run test:watch  | `<target>` | Runs Karma server for a package or element. | npm run test:watch button |
| npm run lint  | `<target>` | Runs linting tools in a package or element. If not define the `<target>`, it will runs linting in all packages. | npm run lint button |
| npm run lint:fix  | `<target>` | Fix linting errors for a package or element. | npm run lint:fix button |


### Commit prefixes

Commit prefixes must be written in a correct pattern when committing code into EF repositories. It will be used to determine running version when release the package and for generating changelogs.

| Prefix | Incremental Version | Usage |
|---|:---:|---|
| `BREAKING CHANGE(<package-name>):` | MAJOR | Changes that breaking existing public API.<br/>**BREAKING CHANGE(coral-button): cta attribute has been removed** |
| `feat(<package-name>):` | MINOR | A new feature.<br/>**feat(coral-button): element sings a song every Sunday** |
| `fix(<package-name>):` | PATCH | A bug fix.<br/>**fix(coral-button): auto-play issue (#39)**|
| `style(<package-name>):` | PATCH | Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc).<br/>**style(coral-button): removed trailing white space** |
| `docs(<package-name>):` | PATCH | Documentation only changes.<br/>**docs(coral-button): included complex sample to README** |
| `refactor(<package-name>):` | PATCH | A code change that neither fixes a bug nor adds a feature.<br/>**refactor(coral-button): changed song picker algorithm** |
| `performance(<package-name>):` | PATCH | A code change that improves performance.<br/>**performance(coral-button): lazy load internal DOM structure** |
| `test(<package-name>):` | PATCH | Add missing tests.<br/>**test(coral-button): increase code coverage to 85%** |
| `chore(<package-name>):` | PATCH | Changes to the build process, dependency updates and other maintenance-related commits.<br/>**chore(coral-button): upgrade dependencies** |
