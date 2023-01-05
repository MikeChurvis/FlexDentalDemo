# Flex Dental Demo

This is the codebase for my pre-interview demonstration for Flex Dental. On its surface, it's a simple To-Do app. Behind the scenes, it's a demonstration.

## Parts

1. A To-Do list app written in **Ember**.
2. A suite of E2E **Playwright** tests that cover the Ember app's behavior.
3. A **React** app built with TDD against those same exact Playwright tests.

### Ember

Represents an application in a legacy project.

- JavaScript
- Bootstrap
- Webpack
- npm

### Playwright

An End-to-End test suite written against the legacy Ember app. Note that the tests themselves exist in their own repository. This repository is included in both the Ember and React projects as a `git submodule`.

### React

Represents an application in a greenfield project. Uses TDD with the Playwright test suite as a scaffold to implement the same features as the legacy app.

- TypeScript
- Tailwind CSS
- Vite
- pnpm

## Checklist

- [x] Scaffold the Ember frontend.
- [x] Scaffold the React frontend.
- [x] Scaffold the Django backend.
- [x] Scaffold the Playwright test runner.
- [x] Create a repo for the Playwright tests themselves.
- [x] Add the e2e test repo as a git submodule to the Playwright test runner.
- [x] Add Playwright to react project.
- [x] Add the e2e test repo as a git submodule to the React frontend.
- [x] Django: Set a custom user auth model. DO NOT PERFORM FIRST MIGRATE UNTIL IT IS IN PLACE.
- [ ] Django: Setup a docker environment with compose.
- [ ] Django: Add .env to .gitignore.
- [ ] Django: Add .env to .dockerignore.
- [ ] Django: Populate sensitive settings from environment variables.
- [ ] Django: perform first migration.
- [ ] Tests: Push a playwright test from the test runner project into the submodule's remote. Pull it into the React project. Run it successfully.
- [ ] Ember: install ember-simple-auth.
- [ ] Ember: install bootstrap.
- [ ] Ember: install sass.
- [ ] Django: create user auth view.
- [ ] Django: create mock login-required view.
- [ ] Ember: mock login page.
- [ ] Ember: setup ember-simple-auth.
- [ ] Ember: confirm that Ember can authenticate through Django.
- [ ] Ember: persist auth token in sessionStorage.
- [ ] React: add Tailwind CSS.
- [ ] React: add React Router.
- [ ] React: persist auth token in sessionStorage.
- [ ] Build both projects into routes of the gh-pages branch.
