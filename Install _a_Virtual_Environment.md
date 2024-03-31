### Installing a Virtual Environment

Virtual environment or **venv** is not an integral part of Django development. However, it is recommended to use it as it is allows you to create multiple virtual Python environments on a single operating system. Thanks to the virtual environment, the application can run independently of the other Python applications.

In principle, it is possible to run applications in Django without a virtual environment. In this case, all Django packages are installed globally. However, what if, after the first app is created, a new version of Django is released? If we want to use a new version of Django for the second project, Then, due to the global installation of packages, you will have to update the first project that uses the old version. This will require some additional upgrading work, as There is not always backward compatibility between packages. If we decide to use the old version for the second project, then we will lose the potential benefits of the new version. And the use of The virtual environment allows you to delimit the packages for each project.

To work with the virtual environment, python uses the built-in venv module

So, let's create a virtual environment. First, let's define a directory for django projects. For example, let's say it's the `C:\django` directory. First of all, let's navigate to this directory in the terminal/command line using the cd command.
  ` cd C:\django`
  
Then, to create a virtual environment, run the following command:
`python -m venv .venv`
The venv module is given the name of the environment, which in this case will be called ".venv". There are no specific conventions for naming virtual environments.
After that, a subdirectory **".venv"** will be created in the current folder (C:\django).

### Activating a Virtual Environment
To use it, the virtual environment must be activated. And every time we work with a Django project, the virtual environment associated with it needs to be activated. For example, let's activate the environment created above, which is located in the current directory in the .venv folder. The activation process is slightly different depending on the operating system and what tools are applied. For example, on Windows, you can use the command line and PowerShell, But there are differences between them.
#### Activation in Windows in the command line
If our OS is Windows, then in the .venv/Scripts/ folder we can find the activate.bat) file that activates virtual environment. For example, on Windows, activating a virtual environment in the command line will look like this:
`.venv\Scripts\activate.bat`
#### Activation in Windows in PowerShell
Also when running on Windows, in the .venv/Scripts/ folder, we can find theactivate.ps1 file, which also activates the virtual environment, but only applies to PowerShell. However, when working with PowerShell, keep in mind that by default it is not allowed to use scripts. Therefore Before you can activate the environment, you must set permissions for the current user. Therefore, to activate the virtual environment in PowerShell, you need to run the following two commands:
`Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
.venv\Scripts\Activate.ps1`
#### Activation on Linux and MacOS
For Linux and MacOS, activation will be done with the following command:
`source .venv/bin/activate`
In the following, I'll provide examples based on the Windows command line, but all the other examples will not depend on whether you are using PowerShell or the command line, Windows, Linux, or MacOS. In any case, after successful activation, to the left of the current directory, we will see the name of the virtual environment in parentheses:
```
C:\Users\eugen>cd C:\django

C:\django>python -m venv .venv

C:\django>.venv\Scripts\activate.bat    Activating the virtual environment 

(.venv) C:\django>    The virtual environment is activated
```
### Installing Django
After activating the virtual environment to install Django, run the following command in the console
`python -m pip install Django`
It installs the latest version of Django.
```
(.venv) C:\django>python -m pip install Django
Collecting Django
  Using cached Django-4.1-py3-none-any.whl (8.1 MB)
Collecting sqlparse>=0.2.2
  Using cached sqlparse-0.4.2-py3-none-any.whl (42 kB)
Collecting tzdata
  Using cached tzdata-2022.1-py2.py3-none-any.whl (339 kB)
Collecting asgiref<4,>=3.5.2
  Using cached asgiref-3.5.2-py3-none-any.whl (22 kB)
Installing collected packages: tzdata, sqlparse, asgiref, Django
Successfully installed Django-4.1 asgiref-3.5.2 sqlparse-0.4.2 tzdata-2022.1
(.venv) C:\django>
```
If we are interested in a specific version of Django, then we can specify it during installation:
`python -m pip install django~=4.0.0`
### Checking the Installation
To make sure everything is installed correctly, we can go to the python interpreter. To do this, enter the command in the terminal
`python`
And then execute the following two instructions sequentially:
```
>>> import django
 >>> print(django.get_version())
```
 The console output in my case is:

```(.venv) C:\django>python
Python 3.10.1 (tags/v3.10.1:2cd268a, Dec  6 2021, 19:10:37) [MSC v.1929 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
 >>> import django
 >>> print(django.get_version())
4.1
>>>
```
#### Deactivating the Virtual Environment
When we are done with the virtual environment, we can deactivate it with the following command:
`deactivate`


