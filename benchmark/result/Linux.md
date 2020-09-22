# Test Environment

 - Thinkpad T490
 - Ubuntu 18.04 LTS
 - Processor 2.8GHz  Quad-Core Intel Core i7
 - Memory 16GB 
 - Disk 150GB (Available)

# Installation

## pipenv

```
Installing dependencies from Pipfile.lock (508a14)…
Installing django-debug-toolbar…
Installing dependencies from Pipfile.lock (e8c445)…

(pipenv) minchul@minchul-ThinkPad-T490:~/pipenvtest$ time pipenv install --dev >> pipenv_install.txt
Creating a virtualenv for this project…
Pipfile: /home/minchul/pipenvtest/Pipfile
Using /home/minchul/.local/share/virtualenvs/pipenv-MJh9xc6v/bin/python3.8 (3.8.1) to create virtualenv…
⠹ Creating virtual environment...created virtual environment CPython3.8.1.final.0-64 in 143ms
  creator CPython3Posix(dest=/home/minchul/.local/share/virtualenvs/pipenvtest-0X_JG6xv, clear=False, global=False)
  seeder FromAppData(download=False, pip=bundle, setuptools=bundle, wheel=bundle, via=copy, app_data_dir=/home/minchul/.local/share/virtualenv)
    added seed packages: pip==20.2.2, setuptools==49.6.0, wheel==0.35.1
  activators BashActivator,CShellActivator,FishActivator,PowerShellActivator,PythonActivator,XonshActivator

✔ Successfully created virtual environment! 
Virtualenv location: /home/minchul/.local/share/virtualenvs/pipenvtest-0X_JG6xv
  🐍   ▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ 19/19 — 00:00:05

real    0m9.384s
user    0m27.665s
sys     0m2.022s
(pipenv) minchul@minchul-ThinkPad-T490:~/pipenvtest$ 
```

> real    0m9.384s  
user    0m27.665s  
sys     0m2.022s


## poetry

```
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

real    0m27.476s
user    0m7.395s
sys     0m1.205s

```

> real    0m27.476s  
user    0m7.395s  
sys     0m1.205s

# Add Dependency

## pipenv

```
(pipenv) minchul@minchul-ThinkPad-T490:~/pipenvtest$ time pipenv install --dev django-debug-toolbar >> pipenv_install.txt
Adding django-debug-toolbar to Pipfile's [dev-packages]…
✔ Installation Succeeded 
Pipfile.lock (508a14) out of date, updating to (e8c445)…
Locking [dev-packages] dependencies…
Building requirements...
Resolving dependencies...
✔ Success! 
Locking [packages] dependencies…
Building requirements...
Resolving dependencies...
✔ Success! 
Updated Pipfile.lock (e8c445)!
  🐍   ▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉▉ 0/0 — 00:00:00

real    0m30.232s
user    0m13.620s
sys     0m1.117s

```

> real    0m30.232s  
user    0m13.620s  
sys     0m1.117s


## poetry

```
minchul@minchul-ThinkPad-T490:~/pycon-session-release/benchmark/src/poetry$ time poetry add --dev django-debug-toolbar >> poetry_add.txt

Using version ^3.0 for django-debug-toolbar

Updating dependencies
Resolving dependencies...

Writing lock file


Package operations: 1 install, 0 updates, 0 removals

  - Installing django-debug-toolbar (3.0)


real    0m22.835s
user    0m2.184s
sys     0m0.172s
```

> real    0m22.835s  
user    0m2.184s  
sys     0m0.172s


# Lock

## pipenv

```
(pipenv) minchul@minchul-ThinkPad-T490:~/pipenvtest$ time pipenv lock >> pipenv_lock.txt
Locking [dev-packages] dependencies…
Building requirements...
Resolving dependencies...
✔ Success! 
Locking [packages] dependencies…
Building requirements...
Resolving dependencies...
✔ Success! 
Updated Pipfile.lock (e8c445)!

real    0m23.854s
user    0m11.049s
sys     0m0.854s
(pipenv) minchul@minchul-ThinkPad-T490:~/pipenvtest$ 

```

> real    0m23.854s  
user    0m11.049s  
sys     0m0.854s


## poetry

```
minchul@minchul-ThinkPad-T490:~/pycon-session-release/benchmark/src/poetry$ time poetry lock >> poetry_lock.txt

Updating dependencies
Resolving dependencies...

real    0m5.091s
user    0m0.867s
sys     0m0.037s
```

> real    0m5.091s  
user    0m0.867s  
sys     0m0.037s


# Remove Dependency

## pipenv

```
(pipenv) 1 minchul@minchul-ThinkPad-T490:~/pipenvtest$ time pipenv uninstall --dev django-debug-toolbar
Uninstalling django-debug-toolbar…
Found existing installation: django-debug-toolbar 3.0
Uninstalling django-debug-toolbar-3.0:
  Successfully uninstalled django-debug-toolbar-3.0

Removing django-debug-toolbar from Pipfile…
Locking [dev-packages] dependencies…
Building requirements...
Resolving dependencies...
✔ Success! 
Locking [packages] dependencies…
Building requirements...
Resolving dependencies...
✔ Success! 
Updated Pipfile.lock (508a14)!

real    0m20.819s
user    0m10.048s
sys     0m0.847s

```

> real    0m20.819s  
user    0m10.048s  
sys     0m0.847s


## poetry

```
minchul@minchul-ThinkPad-T490:~/pycon-session-release/benchmark/src/poetry$ time poetry remove --dev django-debug-toolbar >> poetry_remove.txt

Updating dependencies
Resolving dependencies...

Writing lock file


Package operations: 0 installs, 0 updates, 1 removal

  - Removing django-debug-toolbar (3.0)


real    0m0.901s
user    0m0.820s
sys     0m0.086s
```

> real    0m0.901s  
user    0m0.820s  
sys     0m0.086s
