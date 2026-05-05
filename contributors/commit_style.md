# Commit Message Guidelines

We follow a structured commit message format to ensure a clear and consistent history. Each commit message should adhere to the following convention:

```
type(scope): brief description
```

-   **type**: Represents the kind of change. Common types include:
    -   `feat`: A new feature or enhancement.
    -   `fix`: A bug fix.
    -   `docs`: Documentation only changes.
    -   `style`: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc).
    -   `refactor`: A code change that neither fixes a bug nor adds a feature.
    -   `test`: Adding missing tests or correcting existing tests.
    -   `chore`: Maintenance tasks, build process changes, etc.
-   **scope**: (Optional) Specifies the area of the codebase affected by the change (e.g., `cli`, `linux-page`, `tldr-section`).
-   **brief description**: A concise summary of the change in the present indicative tense.

**Example:**
```
feat(git): add mnu page for git commands
fix(ls-page): correct -a flag description in tldr
docs(contributing): clarify commit message guidelines
```