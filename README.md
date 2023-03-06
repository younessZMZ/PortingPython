# PortingPython
This project is a demo for porting python from an old version x to a new version y.

# Standardize testing in python

Elements of python Project :

- Business logic.
- Tests - unit and integration.
- Packaging.
- Documentation.
- Type checks.
- Static code analysis/ style checks.
- Support multiple Python versions.
- Support multiple versions of dependencies.

Insure all this is good after each commit.

Libraries for each element:

- Tests : pytest, nosetest, nose2.
- Packaging:
  - library: setuptools, flit, poetry.
  - application: PEX, XAR.
- Documentation generation: sphinx, mkdocs.
- Static code analysis/ style check: black, flake8, pylint. 
- Multiple Python versions: virtualenv, pyenv, pipenv.
- Multiple versions of dependencies: virtualenv, pyenv, pipenv.

# TOX

Allows for a python project:

- To define all tools in one place.
- With their configuration.
- While having a central way of invoking each of them.
- Inside an isolated and reproducible environment.

## Tox what it is

Python cli tool:

- install via:
  - pip install tox
- invoke via:
  - python -m tox
  - tox
- manage, create and run reproducible test environments.

# Porting steps

- Have a good test coverage: use coverage.py.
  If you want a number to aim for, try to get over 80% coverage.
- Learn the differences between the two versions.
  Typically the two best ways of doing that is reading the “What’s New” doc for each release of Python 3
  and the Porting to Python 3 book (which is free online).
  There is also a handy cheat sheet from the Python-Future project.
- Update your code:
  Use Futurize and Modernize and write code supported by both versions.
- Rely on your tests in order to make code work again.
- Start using new version in production.
- Remove the old version compatibility.

Here are the steps given by ChatGPT:

- Make sure you have a backup of your project before making any changes.

- Check the compatibility of your project's dependencies and libraries with Python 3.10. Update or replace any that are not compatible.

- Run your project's tests to ensure that everything is working as expected.

- Use a tool like "2to3" to automatically convert your code from Python 2 to Python 3. You can also use "python-modernize" to make your code compatible with Python 3.10.

- Check the official documentation of Python 3.10 to see if there are any new features or changes that could affect your project.

- Test your project thoroughly to make sure that everything is working as expected.

- Finally, deploy your project to a production environment after testing it in a staging environment.

# Project Migration:

1. Migrate internal packages to support both Python 3.6 and 3.9.
2. Migrate parent classes to the leaves by following these steps:
   1. Run the class on both versions to ensure that every line of code works as expected.
   2. Make the necessary changes to ensure that the code behaves as expected under both versions.
   3. Test multiple cases.
3. Put the code into production. 
4. Create a new environment for production with Python 3.9. 
5. Run batches of scripts in production using the new environment.
6. 