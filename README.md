# Final Project Python Basics

## 1. Installing the package locally
To install the package locally (for example, to use it like any other installed Python package), open a terminal, navigate to the directory containing `setup.py` and run:
```
pip install .
```
This will install your package in the current Python environment.

## 2. Installation in editable mode (for development)
If you plan to further develop your package, you may want to install it in the so-called `editable` mode. This will allow you to make changes to the package code and reflect them immediately without reinstalling. To do this, use:
```
pip install -e .
```
The above command should also be run in the directory with the `setup.py` file.

## 3. Building distribution
If you want to share your package with others or publish it on Python Package Index (PyPI), you must first build a distribution. In the terminal, in the directory with `setup.py`, run:
```
python setup.py sdist bdist_wheel
```
This will create a source distribution (sdist) and a wheel distribution (wheel) in the `dist/` directory. These files can then be uploaded to PyPI.

## 4. Uploading to PyPI
To upload a package to PyPI, you must first install `twine`, if you haven't already done so:
```
pip install twine
```
Then, use `twine` to upload your distribution files to PyPI:
```
twine upload dist/*
```
You will need to enter your PyPI username and password to continue.

## Important notes
- Before publishing your package on PyPI, make sure you have a unique name for your package. You can check the availability of the name by searching PyPI.
- Consider adding a `requirements.txt` file to your project if your package depends on other packages. Although `install_requires` in `setup.py` handles dependencies when installing a package, `requirements.txt` is useful for users who want to install dependencies with `pip install -r requirements.txt`.
- Remember to maintain versioning of your project and update the version number in `setup.py` with each change you want to publish.


## File code `setup.py`.
```
from setuptools import setup, find_packages

setup(
    name="final_project_python_basics",
    version="0.1.0",
    packages=find_packages(),
    entry_points={
        'console_scripts': [
            'myassistant=final_project_python_basics.main:main',
        ],
    },
    author="Twoje Imię",
    author_email="twoj.email@example.com",
    description="A personal assistant application for managing contacts, notes, birthdays, etc.",
    keywords="Personal Assistant, Contacts, Notes, Birthdays",
    license="MIT",
    long_description=open('README.md').read(),
    long_description_content_type='text/markdown',
    install_requires=[
        # Tutaj dodaj zależności, np. 'requests>=2.25.1',
        # Jeśli Twój projekt nie ma zależności zewnętrznych, tę sekcję można pominąć
    ],
    python_requires='>=3.6',
    classifiers=[
        "Programming Language :: Python :: 3",
        "License :: OSI Approved :: MIT License",
        "Operating System :: OS Independent",
    ],
)
```
In the code above:
- `name` is the name of your package.
- `version` is the current version of your package.
- `packages=find_packages()`, automatically finds packages to include. Make sure your modules/packages are properly structured in directories.
- `entry_points` defines the entry point to your application, so you can run it from the command line. Modify the path final_project_python_basics.main:main according to the actual location of the main function in your project.
- `author`, `author_email`, `description`, `keywords` and `license` are metadata describing your project.
- `long_description` can contain a longer description, which is usually loaded from the README file.
- `install_requires` allows you to define the dependencies that must be installed with your package. If your project depends on external Python libraries, list them here.
- `python_requires` specifies the Python versions compatible with your package.
- `classifiers` are a list of classifiers that help others find your project on PyPI and understand its context.

## Use of:

The application can be run from the command line after installation:
```
myassistant
```

## Development

The project is under development. Any suggestions and bug reports are welcome.

## License

The project is made available under the MIT license. Please refer to the LICENSE file for details.

## Author

Group 2
