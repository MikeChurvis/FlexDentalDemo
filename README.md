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

- [x] Create the Ember project.
- [x] Upload the Ember project repo to GitHub.
- [ ] Create the React project.
- [ ] Upload the React project repo to GitHub.
- [ ] Create a repo for the Playwright tests.
- [ ] Upload the Playwright repo to GitHub.
- [ ] Import the Playwright repo into Ember.
