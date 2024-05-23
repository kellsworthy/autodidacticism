# Cheat Sheet: Poetry

## About Poetry

Poetry is what I chose to manage packages, virtual environments, and dependencies! My hope is that it'll reduce the amount of packages I need to keep track of.

*See [Real Python's tutorial](https://realpython.com/dependency-management-python-poetry/) for an amazingly in-depth walkthrough!*

## Creating new projects

1. Use `poetry new --src [project-name]` to create the project's file structure.
    - The `--src` will use a `src` layout. See the [Python Packaging User Guide](https://packaging.python.org/en/latest/discussions/src-layout-vs-flat-layout/) for more details.
2. Open an integrated terminal from the new project folder and run `poetry env use python3` to create a virtual environment specific to the project.
    - I can also specify initial packages an dependencies. Use `--help` to learn these commands.
3. Use `poetry env info --path` to display the virtual environment information and confirm that it is located in your project.
4. Go to **Python: Select Interpreter** in VSCode's command bar, select "Enter interpreter path...", and enter the path from the last step.
    - The interpreter should now reflect `Python 3.xx.x ('.venv': Poetry)`.
5. If using Poetry only for dependency management, set the `package-mode` to `true` in the `pyproject.toml` file.
    - Skip this step if using Poetry for packaging and/or publishing.

## While working

- Confirm you are using the correct interpreter by running `which python3` in the project's terminal.
- Confirm you are using the correct virtual environment by running `poetry env info --path`.
- Use `poetry add [package-name]` to find a [PyPI](https://pypi.org) package, install it, and automatically add it to the project's dependencies.
- Use `poetry run [your_script.py | command-line-tool-name]` to run Python scripts or command line tools.
- Use `poetry install` to resolve all dependencies listed in the `pyproject.toml` file, downloads their latest versions, and writes all packages/versions to a `poetry.lock` file.
  - Committing this file to a project is important so that anyone who sets up the project will use the exact same versions (including my future self).
- Use `poetry update` to update all dependencies to the latest versions according to your `pyproject.toml` file and write them to the lock file.

## Virtual environments

- Use `poetry env info --path` to check the path of the current activated virtual environment.
