# hello-poetry

[Poetry](https://python-poetry.org/docs/) is a tool for dependency management and packaging in Python. It allows you to declare the libraries your project depends on and it will manage (install/update) them for you.


<br>

## Installation

```
curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python
```

- add line `source $HOME/.poetry/env` to `.bashrc` or else you have to manually run this command each and every time you start off a terminal
- run `poetry --version` to verify the installation

<br>

## 1. Create a new project

- `poetry new hello-poetry` - will create a new directory called hello-poetry which will have few default files

<br>

## 2. Important Concepts

- `pyproject.toml` - will take care of project maintanence and its dependencies
- Inside `pyproject.toml` there is a section called `tool.poetry.dependencies` under which you can add your dependencies either by manually adding

```
[tool.poetry.dependencies]
pendulum = "^1.4"
```

or we can use `add` command

```
poetry add pendulum
```

<br>

## 3. The lock file

```
poetry install
``` 

- Poetry simply resolves all dependencies listed in your `pyproject.toml` file and it writes all of the packages and the exact versions of them that it downloaded to the `poetry.lock` file
- Commit your poetry.lock file to version control, becuase it will let users who sets up the project to use the exact same versions of the dependencies that you are using.

<br>

## Other useful commands

- `poetry build` - will package your library in two different formats: `sdist` which is the `source` format, and `wheel` which is a `compiled` package.

- `poetry publish` -  will package and publish the library to PyPI, at the condition that you are a registered user and you have [configured your credentials](https://python-poetry.org/docs/repositories/#adding-credentials) properly.

<br>

## Note

version `^1.4` means `>=1.4.0 <2.0.0`
