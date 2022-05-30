# Install `pipenv`

## Prepare (things to check before doing install):
1. Verify `python` is installed:  
`python --version`  
Sample output:  
    ```
    PS C:\Users\User\Programming\pipenv-example-basic> python --version
    Python 3.10.4
    ```

1. Verify `pip` is installed:  
`pip --version`  
Sample ouput:  
    ```
    PS C:\Users\User\Programming\pipenv-example-basic> pip --version
    pip 22.0.4 from C:\Users\User\AppData\Local\Programs\Python\Python310\lib\site-packages\pip (python 3.10)
    ```

1. Check currently installed packages:  
`pip list`  
Sample output:  
    ```
    PS C:\Users\User\Programming\pipenv-example-basic> pip list
    Package    Version
    ---------- -------
    pip        22.0.4
    setuptools 58.1.0
    WARNING: You are using pip version 22.0.4; however, version 22.1.1 is available.
    You should consider upgrading via the 'C:\Users\User\AppData\Local\Programs\Python\Python310\python.exe -m pip install --upgrade pip' command.
    ```

  1. Upgrade `pip`:  
  `C:\Users\User\AppData\Local\Programs\Python\Python310\python.exe -m pip install --upgrade pip`  
  Sample output:  
      ```
      PS C:\Users\User\Programming\pipenv-example-basic> C:\Users\User\AppData\Local\Programs\Python\Python310\python.exe -m pip install --upgrade pip
      Requirement already satisfied: pip in c:\users\user\appdata\local\programs\python\python310\lib\site-packages (22.0.4)
      Collecting pip
        Using cached pip-22.1.1-py3-none-any.whl (2.1 MB)
      Installing collected packages: pip
        Attempting uninstall: pip
          Found existing installation: pip 22.0.4
          Uninstalling pip-22.0.4:
            Successfully uninstalled pip-22.0.4
      Successfully installed pip-22.1.1
      ```

1. Check currently installed packages:  
`pip list`  
Sample output:  
    ```
    PS C:\Users\User\Programming\pipenv-example-basic> pip list
    Package    Version
    ---------- -------
    pip        22.1.1
    setuptools 58.1.0
    ```

## Process:
1. Install `pipenv`:  
`pip install --user pipenv`  
Sample output:  
    ```
    PS C:\Users\User\Programming\pipenv-example-basic> pip install --user pipenv
    Collecting pipenv
      Downloading pipenv-2022.5.2-py2.py3-none-any.whl (3.9 MB)
        ---------------------------------------- 3.9/3.9 MB 6.4 MB/s eta 0:00:00
    Collecting virtualenv
      Downloading virtualenv-20.14.1-py2.py3-none-any.whl (8.8 MB)
        ---------------------------------------- 8.8/8.8 MB 14.8 MB/s eta 0:00:00
    Collecting certifi
      Downloading certifi-2022.5.18.1-py3-none-any.whl (155 kB)
        ---------------------------------------- 155.2/155.2 KB 9.1 MB/s eta 0:00:00
    Collecting virtualenv-clone>=0.2.5
      Downloading virtualenv_clone-0.5.7-py3-none-any.whl (6.6 kB)
    Requirement already satisfied: pip>=22.0.4 in c:\users\user\appdata\local\programs\python\python310\lib\site-packages (from pipenv) (22.0.4)
    Requirement already satisfied: setuptools>=36.2.1 in c:\users\user\appdata\local\programs\python\python310\lib\site-packages (from pipenv) (58.1.0)
    Collecting distlib<1,>=0.3.1
      Downloading distlib-0.3.4-py2.py3-none-any.whl (461 kB)
        ---------------------------------------- 461.2/461.2 KB 28.2 MB/s eta 0:00:00
    Collecting filelock<4,>=3.2
      Downloading filelock-3.7.0-py3-none-any.whl (10 kB)
    Collecting six<2,>=1.9.0
      Downloading six-1.16.0-py2.py3-none-any.whl (11 kB)
    Collecting platformdirs<3,>=2
      Downloading platformdirs-2.5.2-py3-none-any.whl (14 kB)
    Installing collected packages: distlib, virtualenv-clone, six, platformdirs, filelock, certifi, virtualenv, pipenv
      WARNING: The script virtualenv-clone.exe is installed in 'C:\Users\User\AppData\Roaming\Python\Python310\Scripts' which is not on PATH.
      Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
      WARNING: The script virtualenv.exe is installed in 'C:\Users\User\AppData\Roaming\Python\Python310\Scripts' which is not on PATH.
      Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
      WARNING: The scripts pipenv-resolver.exe and pipenv.exe are installed in 'C:\Users\User\AppData\Roaming\Python\Python310\Scripts' which is not on PATH.
      Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
    Successfully installed certifi-2022.5.18.1 distlib-0.3.4 filelock-3.7.0 pipenv-2022.5.2 platformdirs-2.5.2 six-1.16.0 virtualenv-20.14.1 virtualenv-clone-0.5.7
    WARNING: You are using pip version 22.0.4; however, version 22.1.1 is available.
    You should consider upgrading via the 'C:\Users\User\AppData\Local\Programs\Python\Python310\python.exe -m pip install --upgrade pip' command.
    ```

1. Note the `Scripts` location and copy it:  
Sample location:  
`C:\Users\User\AppData\Roaming\Python\Python310\Scripts`  

1. Add location of this specific `Scripts` directory `C:\Users\User\AppData\Roaming\Python\Python310\Scripts` to user `PATH` variable:  
  * Windows Key >> search 'path' >> select 'Edit the system environment variables' >> choose 'Environment Variables' button near bottom right >> double click 'path' line in 'User variables for User' >> click 'New' >> paste in absolute route copied previously into new line >> click 'OK' to close "Edit environment variable" dialogue >> click 'OK' to close "Environment variables" page >> click 'OK' to close "System Properties" page.

    * ![edit_system_environment_variables_choice](https://user-images.githubusercontent.com/47562501/170906540-c47125b3-4f33-4bbc-a407-2fc206a9008c.png)

    * ![environment_variables_button](https://user-images.githubusercontent.com/47562501/170906596-90fa146e-e74b-486f-97d4-23ed83b67c03.png)

    * ![click_path_variable](https://user-images.githubusercontent.com/47562501/170906635-20d23679-bdb1-4721-a4e3-be7d44082dd3.png)

    * ![add_scripts_directory_location_to_path](https://user-images.githubusercontent.com/47562501/170906653-4a5d3ec1-390e-460a-9073-9351a61aafb7.png)

    * ![click_ok_to_save_path](https://user-images.githubusercontent.com/47562501/170906678-429f4084-b125-4ebb-9bd5-401139074908.png)

    * ![click_ok_to_close_user_variables](https://user-images.githubusercontent.com/47562501/170906707-5d55bce6-05cc-49e7-b868-9139dc81f4b8.png)

    * ![click_ok_to_close_system_properties_dialog](https://user-images.githubusercontent.com/47562501/170906732-3f11e3f1-7a24-44d8-9233-6f59d6598144.png)

1. Verify `pipenv` install:  
`pipenv --version`  
Sample output:  
    ```
    PS C:\Users\User\Programming> pipenv --version
    pipenv: The term 'pipenv' is not recognized as a name of a cmdlet, function, script file, or executable program.
    Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
    ```

1. Restart terminal shell.

1. Verify `pipenv` install:  
`pipenv --version`  
Sample output:  
    ```
    PS C:\Users\User\Programming> pipenv --version
    pipenv, version 2022.5.2
    ```

1. Check new currently installed packages:  
`pip list`  
Sample output:  
    ```
    PS C:\Users\User\Programming> pip list
    Package          Version
    ---------------- -----------
    certifi          2022.5.18.1
    distlib          0.3.4
    filelock         3.7.0
    pip              22.1.1
    pipenv           2022.5.2
    platformdirs     2.5.2
    setuptools       58.1.0
    six              1.16.0
    virtualenv       20.14.1
    virtualenv-clone 0.5.7
    ```

