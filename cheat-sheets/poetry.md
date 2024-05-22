# Cheat Sheet: Poetry

## About Poetry

Poetry is what I chose to manage packages, virtual environments, and dependencies! My hope is that it'll reduce the amount of packages I need to keep track of.

*See [Real Python's tutorial](https://realpython.com/dependency-management-python-poetry/) for an amazingly in-depth walkthrough!*

## Creating new projects

1. Create a folder where I'd like my project to be located (or open an existing folder).
2. Use `poetry new [project-name] --src` to create the project.
    - The `--src` will use a `src` layout. See the [Python Packaging User Guide](https://packaging.python.org/en/latest/discussions/src-layout-vs-flat-layout/) for more details.
3. Use `poetry init` to create a virtual environment specific to the project.
    - I can also specify initial packages an dependencies. Use `--help` to learn these commands.
4. **VS Code** should automatically detect the environment and make it available to select as the project's Python interpreter.
5. If using Poetry only for dependency management, set the `package-mode` to `true` in the `pyproject.toml` file.
    - Skip this step if using Poetry for packaging and/or publishing.

## While working

- Use `poetry add [package-name]` to find a [PyPI](https://pypi.org) package, install it, and automatically add it to the project's dependencies.
- Use `poetry run [your_script.py | command-line-tool-name]` to run Python scripts or command line tools.
- Use `poetry install` to resolve all dependencies listed in the `pyproject.toml` file, downloads their latest versions, and writes all packages/versions to a `poetry.lock` file.
  - Committing this file to a project is important so that anyone who sets up the project will use the exact same versions (including my future self).
- Use `poetry update` to update all dependencies to the latest versions according to your `pyproject.toml` file and write them to the lock file.

## Virtual environments

- Use `poetry env info --path` to check the path of the current activated virtual environment.
