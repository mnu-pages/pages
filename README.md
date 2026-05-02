# MNU Pages

> «Our job is not to make things complex, but to make them simple and understandable.»

MNU Pages is a collection of simplified, human-readable documentation for CLI tools. These pages are designed to be **clear**, **calm**, and **actually helpful**.

## The Goal
Someone with zero knowledge should be able to read an MNU page once and say, "Oh… I get it now." We focus on the fundamental commands and the mental model of the tool to build user confidence.

## How it Works
Each page is written in a custom `.mn` format designed for clarity.
- **Description:** A simple explanation of what the tool is.
- **Examples:** Raw, copy-pasteable commands.
- **Explanations:** A human-to-human breakdown of what the command does.
- **Summary:** A practical habit or best practice.

## Directory Structure
- `cli/`: General-purpose tools (git, docker, tar).
- `linux/`: Linux-specific commands.
- `windows/`: Tools for the Windows environment.
- `mac/`: macOS-specific utilities.
- `examples/`: Reference templates for new pages.

## Available clients
- **Nodejs client**:
  ```bash
  npm i -g mnu-pages
  ```

## Contributing
If you want to help make the terminal less intimidating, please read our [CONTRIBUTING.md](CONTRIBUTING.md) for style and formatting guidelines. You can find reference templates in the [examples/](examples/) directory.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
