# CommitMessages
Self documentation page for commit messages

## Table of Contents

- [Conventional Commit Message Types](conventional-commit-message-types)
- [Breaking Changes](breaking-changes)
- [Issue References in Footer](issue-references-in-footer)


## Conventional Message Types

| Type       | Purpose                                                       | Format Example                        | Example Message                                           |
|------------|---------------------------------------------------------------|----------------------------------------|-----------------------------------------------------------|
| `feat`     | Introduce a new feature                                       | `feat(scope): message`                | `feat(auth): add OAuth2 login`                           |
| `fix`      | Fix a bug                                                     | `fix(scope): message`                 | `fix(api): correct null user check`                      |
| `docs`     | Documentation changes only                                    | `docs(scope): message`                | `docs(readme): update install instructions`              |
| `style`    | Code style changes (no logic impact)                          | `style(scope): message`               | `style(ui): reformat button spacing`                     |
| `refactor` | Code changes (not a fix or feature)                           | `refactor(scope): message`            | `refactor(db): simplify query builder logic`             |
| `perf`     | Improve performance                                           | `perf(scope): message`                | `perf(cache): optimize query results caching`            |
| `test`     | Add or fix tests                                              | `test(scope): message`                | `test(user): add unit tests for registration flow`       |
| `chore`    | Misc. tasks (e.g., build tools, configs, version bumps)       | `chore(scope): message`               | `chore(deps): update Moq to v4.16.1`                     |
| `build`    | Changes to build system or dependencies                       | `build(scope): message`               | `build(gradle): update compileSdkVersion`                |
| `ci`       | CI/CD configuration changes                                   | `ci(scope): message`                  | `ci(github): add PR labeler workflow`                    |



## Breaking Changes

| Usage             | Format                     | Example                                                                 |
|------------------|----------------------------|-------------------------------------------------------------------------|
| In subject        | `type(scope)!: message`    | `feat(api)!: change response structure`                                |
| In footer         | `BREAKING CHANGE:`         | `BREAKING CHANGE: removed legacy login method. Use /auth/login instead.`|



## Issue References in Footer

| Purpose             | Format              | Example               |
|---------------------|---------------------|------------------------|
| Close an issue      | `Closes: #123`      | `Closes: #456`         |
| Fix a bug/issue     | `Fixes: #123`       | `Fixes: #789`          |
| Reference issue     | `Refs: #123`        | `Refs: #101112`        |
