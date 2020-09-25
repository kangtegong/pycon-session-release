# Test Environment

 - MacBook Pro (15 inch, 2017)
 - MacOS Catalina (Ver. 10.15.6)
 - Processor 2.8GHz  Quad-Core Intel Core i7
 - Memory 16GB 2133 MHz LPDDR3
 - Disk 150GB (Available)

# Installation

## pipenv installation

```
seulaui-MacBook-Pro:pipenv seulapark$ ls
Pipfile		Pipfile.lock
seulaui-MacBook-Pro:pipenv seulapark$ time pipenv install --dev
Warning: the environment variable LANG is not set!
We recommend setting this in ~/.profile (or equivalent) for proper expected behavior.
Creating a virtualenv for this project…
Pipfile: /Users/seulapark/Desktop/Python/pipenv/Pipfile
Using /Library/Frameworks/Python.framework/Versions/3.8/bin/python3.8 (3.8.5) to create virtualenv…
⠹ Creating virtual environment...created virtual environment CPython3.8.5.final.0-64 in 858ms
  creator CPython3Posix(dest=/Users/seulapark/.local/share/virtualenvs/pipenv-FSYgmJuV, clear=False, global=False)
  seeder FromAppData(download=False, pip=bundle, setuptools=bundle, wheel=bundle, via=copy, app_data_dir=/Users/seulapark/Library/Application Support/virtualenv)
    added seed packages: pip==20.2.2, setuptools==49.6.0, wheel==0.35.1
  activators BashActivator,CShellActivator,FishActivator,PowerShellActivator,PythonActivator,XonshActivator
:heavy_check_mark: Successfully created virtual environment!
Virtualenv location: /Users/seulapark/.local/share/virtualenvs/pipenv-FSYgmJuV
Installing dependencies from Pipfile.lock (508a14)…
Ignoring atomicwrites: markers ‘sys_platform == “win32"’ don’t match your environment
Ignoring colorama: markers ‘sys_platform == “win32”’ don’t match your environment
  :snake:   ▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ 21/21 — 00:00:06
To activate this project’s virtualenv, run pipenv shell.
Alternatively, run a command inside the virtualenv with pipenv run.
real	0m15.993s
user	0m32.120s
sys	0m5.568s
```

> real	0m15.993s  
user	0m32.120s  
sys	0m5.568s

## Poetry Installation

```
seulaui-MacBook-Pro:poetry seulapark$ ls
poetry.lock	pyproject.toml
seulaui-MacBook-Pro:poetry seulapark$ time poetry install
Creating virtualenv benchmark-N-THgl5R-py3.8 in /Users/seulapark/Library/Caches/pypoetry/virtualenvs
Installing dependencies from lock file
Package operations: 19 installs, 0 updates, 0 removals
  - Installing asgiref (3.2.10)
  - Installing pyparsing (2.4.7)
  - Installing pytz (2020.1)
  - Installing six (1.15.0)
  - Installing sqlparse (0.3.1)
  - Installing attrs (20.2.0)
  - Installing django (3.1.1)
  - Installing iniconfig (1.0.1)
  - Installing mccabe (0.6.1)
  - Installing more-itertools (8.5.0)
  - Installing packaging (20.4)
  - Installing pluggy (0.13.1)
  - Installing py (1.9.0)
  - Installing pycodestyle (2.6.0)
  - Installing pyflakes (2.2.0)
  - Installing toml (0.10.1)
  - Installing djangorestframework (3.11.1)
  - Installing flake8 (3.8.3)
  - Installing pytest (6.0.2)
real	0m39.619s
user	0m14.999s
sys	0m7.788s
seulaui-MacBook-Pro:poetry seulapark$
```

> real	0m39.619s  
user	0m14.999s  
sys	0m7.788s

# Add dependency

## pipenv add package

```
seulaui-MacBook-Pro:pipenv seulapark$ time pipenv install --dev django-debug-toolbar
Installing django-debug-toolbar…
Adding django-debug-toolbar to Pipfile’s [dev-packages]…
:heavy_check_mark: Installation Succeeded
Pipfile.lock (508a14) out of date, updating to (e8c445)…
Locking [dev-packages] dependencies…
Building requirements...
Resolving dependencies...
:heavy_check_mark: Success!
Locking [packages] dependencies…
Building requirements...
Resolving dependencies...
:heavy_check_mark: Success!
Updated Pipfile.lock (e8c445)!
Installing dependencies from Pipfile.lock (e8c445)…
  :snake:   ▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ 0/0 — 00:00:00
To activate this project’s virtualenv, run pipenv shell.
Alternatively, run a command inside the virtualenv with pipenv run.
real	0m26.962s
user	0m16.101s
sys	0m2.549s
seulaui-MacBook-Pro:pipenv seulapark$
```
> real	0m26.962s  
user	0m16.101s  
sys	0m2.549s

## poetry add package

```
seulaui-MacBook-Pro:poetry seulapark$ time poetry add --dev django-debug-toolbar
Using version ^3.0 for django-debug-toolbar
Updating dependencies
Resolving dependencies... (12.1s)
Writing lock file
Package operations: 1 install, 0 updates, 0 removals
  - Installing django-debug-toolbar (3.0)
real	0m14.678s
user	0m1.872s
sys	0m0.461s
seulaui-MacBook-Pro:poetry seulapark$
```
> real	0m14.678s  
user	0m1.872s  
sys	0m0.461s

# lock dependencies

## pipenv lock

```
seulaui-MacBook-Pro:pipenv seulapark$ time pipenv lock
Locking [dev-packages] dependencies…
Building requirements...
Resolving dependencies...
:heavy_check_mark: Success!
Locking [packages] dependencies…
Building requirements...
Resolving dependencies...
:heavy_check_mark: Success!
Updated Pipfile.lock (e8c445)!
real	0m16.373s
user	0m11.597s
sys	0m1.448s
```

> real	0m16.373s  
user	0m11.597s  
sys	0m1.448s


## poetry lock 

```
seulaui-MacBook-Pro:poetry seulapark$ time poetry lock
Updating dependencies
Resolving dependencies... (2.0s)
real	0m2.622s
user	0m0.884s
sys	0m0.168s
seulaui-MacBook-Pro:poetry seulapark$
```

> real	0m2.622s  
user	0m0.884s  
sys	0m0.168s


# remove package

## pipenv remove

```
seulaui-MacBook-Pro:pipenv seulapark$ time pipenv uninstall --dev pytest
Uninstalling pytest…
Found existing installation: pytest 6.0.2
Uninstalling pytest-6.0.2:
  Successfully uninstalled pytest-6.0.2
Removing pytest from Pipfile…
Locking [dev-packages] dependencies…
Building requirements...
Resolving dependencies...
:heavy_check_mark: Success!
Locking [packages] dependencies…
Building requirements...
Resolving dependencies...
:heavy_check_mark: Success!
Updated Pipfile.lock (3eb60c)!
real	0m12.188s
user	0m8.886s
sys	0m1.242s
```
> real	0m12.188s  
user	0m8.886s  
sys	0m1.242s



## poetry remove

```
seulaui-MacBook-Pro:poetry seulapark$ time poetry remove --dev pytest
Updating dependencies
Resolving dependencies... (0.1s)
Writing lock file
Package operations: 0 installs, 0 updates, 10 removals
  - Removing attrs (20.2.0)
  - Removing iniconfig (1.0.1)
  - Removing more-itertools (8.5.0)
  - Removing packaging (20.4)
  - Removing pluggy (0.13.1)
  - Removing py (1.9.0)
  - Removing pyparsing (2.4.7)
  - Removing pytest (6.0.2)
  - Removing six (1.15.0)
  - Removing toml (0.10.1)
real	0m4.814s
user	0m3.595s
sys	0m1.087s
```

> real	0m4.814s  
user	0m3.595s  
sys	0m1.087s