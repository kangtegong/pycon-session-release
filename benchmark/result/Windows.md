# Test Environment 

 - Thinkpad T490
 - Microsoft Windows 10 Pro
 - Processor 2.8GHz  Quad-Core Intel Core i7
 - Memory 16GB 
 - Disk 150GB (Available)

 > Liunx 때와 동일한 컴퓨터에서 진행

# Installation

## pipenv installation

```
tegon@DESKTOP-AMFQD1R MINGW64 ~/Desktop/pycon/pycon-session-release/benchmark/src/pipenv (master)
$ time pipenv install --dev
Creating a virtualenv for this project??
Pipfile: C:\Users\tegon\Desktop\pycon\pycon-session-release\benchmark\src\pipenv\Pipfile
Using C:/Users/tegon/AppData/Local/Programs/Python/Python38-32/python.exe (3.8.5) to create virtualenv??
[   =] Creating virtual environment...created virtual environment CPython3.8.5.final.0-32 in 449ms
  creator CPython3Windows(dest=C:\Users\tegon\.virtualenvs\pipenv-wCoKZ3H-, clear=False, global=False)
  seeder FromAppData(download=False, pip=bundle, setuptools=bundle, wheel=bundle, via=copy, app_data_dir=C:\Users\tegon\AppData\Local\pypa\virtualenv)
    added seed packages: pip==20.2.2, setuptools==49.6.0, wheel==0.35.1
  activators BashActivator,BatchActivator,FishActivator,PowerShellActivator,PythonActivator,XonshActivator

Successfully created virtual environment!
Virtualenv location: C:\Users\tegon\.virtualenvs\pipenv-wCoKZ3H-
Installing dependencies from Pipfile.lock (508a14)??
To activate this project's virtualenv, run pipenv shell.
Alternatively, run a command inside the virtualenv with pipenv run.

real    0m27.184s
user    0m0.015s
sys     0m0.016s
```

> real    0m27.184s  
user    0m0.015s  
sys     0m0.016s

## poetry installation

```
tegon@DESKTOP-AMFQD1R MINGW64 ~/Desktop/pycon/pycon-session-release/benchmark/src/poetry (master)
$ time poetry install
Installing dependencies from lock file


Package operations: 13 installs, 0 updates, 0 removals

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

real    1m13.574s
user    0m0.015s
sys     0m0.030s
```

> real    1m13.574s  
user    0m0.015s  
sys     0m0.030s


# Add depndency

## pipenv add package

```
tegon@DESKTOP-AMFQD1R MINGW64 ~/Desktop/pycon/pycon-session-release/benchmark/src/pipenv (master)
$ time pipenv install --dev django-debug-toolbar
Installing django-debug-toolbar??
Adding django-debug-toolbar to Pipfile's [dev-packages]??
Installation Succeeded
Pipfile.lock (508a14) out of date, updating to (e8c445)??
Locking [dev-packages] dependencies??
Building requirements...
Resolving dependencies...
[=   ] Locking..Success!
Locking [packages] dependencies??
Building requirements...
Resolving dependencies...
[=== ] Locking..Success!
Updated Pipfile.lock (e8c445)!
Installing dependencies from Pipfile.lock (e8c445)??
To activate this project's virtualenv, run pipenv shell.
Alternatively, run a command inside the virtualenv with pipenv run.

real    0m41.145s
user    0m0.015s
sys     0m0.015s
```
> real    0m41.145s  
user    0m0.015s  
sys     0m0.015s


## poetry add package

```
tegon@DESKTOP-AMFQD1R MINGW64 ~/Desktop/pycon/pycon-session-release/benchmark/src/poetry (master)
$ time poetry add --dev django-debug-toolbar
Using version ^3.1 for django-debug-toolbar

Updating dependencies
Resolving dependencies... (14.3s)

Writing lock file


Package operations: 1 install, 0 updates, 0 removals

  - Installing django-debug-toolbar (3.1)

real    0m19.368s
user    0m0.015s
sys     0m0.015s
```

> real    0m19.368s  
user    0m0.015s  
sys     0m0.015s

# lock dependencies

## pipenv lock

```
tegon@DESKTOP-AMFQD1R MINGW64 ~/Desktop/pycon/pycon-session-release/benchmark/src/pipenv (master)
$ time pipenv lock
Locking [dev-packages] dependencies??
Building requirements...
Resolving dependencies...
[=   ] Locking..Success!
Locking [packages] dependencies??
Building requirements...
Resolving dependencies...
[====] Locking..Success!
Updated Pipfile.lock (e8c445)!

real    0m21.906s
user    0m0.000s
sys     0m0.015s
```

> real    0m21.906s  
user    0m0.000s  
sys     0m0.015s


## poetry lock

```
tegon@DESKTOP-AMFQD1R MINGW64 ~/Desktop/pycon/pycon-session-release/benchmark/src/poetry (master)
$ time poetry lock
Updating dependencies
Resolving dependencies... (4.6s)

real    0m5.626s
user    0m0.031s
sys     0m0.015s
```

> real    0m5.626s  
user    0m0.031s  
sys     0m0.015s


# remove package

## pipenv remove

```
tegon@DESKTOP-AMFQD1R MINGW64 ~/Desktop/pycon/pycon-session-release/benchmark/src/pipenv (master)
$ time pipenv uninstall --dev pytest
Uninstalling pytest??
Found existing installation: pytest 6.0.2
Uninstalling pytest-6.0.2:
  Successfully uninstalled pytest-6.0.2

Removing pytest from Pipfile??
Locking [dev-packages] dependencies??
Building requirements...
Resolving dependencies...
[=== ] Locking..Success!
Locking [packages] dependencies??
Building requirements...
Resolving dependencies...
[    ] Locking..Success!
Updated Pipfile.lock (3eb60c)!

real    0m16.064s
user    0m0.000s
sys     0m0.015s
```

> real    0m16.064s  
user    0m0.000s  
sys     0m0.015s


## poetry remove

```
tegon@DESKTOP-AMFQD1R MINGW64 ~/Desktop/pycon/pycon-session-release/benchmark/src/poetry (master)
$ time poetry remove --dev pytest
Updating dependencies
Resolving dependencies... (0.1s)

Writing lock file


Package operations: 0 installs, 0 updates, 12 removals

  - Removing atomicwrites (1.4.0)
  - Removing attrs (20.2.0)
  - Removing colorama (0.4.3)
  - Removing iniconfig (1.0.1)
  - Removing more-itertools (8.5.0)
  - Removing packaging (20.4)
  - Removing pluggy (0.13.1)
  - Removing py (1.9.0)
  - Removing pyparsing (2.4.7)
  - Removing pytest (6.0.2)
  - Removing six (1.15.0)
  - Removing toml (0.10.1)

real    0m8.435s
user    0m0.000s
sys     0m0.031s
```

> real    0m8.435s  
user    0m0.000s  
sys     0m0.031s
