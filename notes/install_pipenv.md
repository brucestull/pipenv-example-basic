# Install `pipenv`

## Prepare (things to check before doing install):
1. Verify `python` is installed:  
`python --version`  
Sample output:  
    ```
    PS C:\Users\Bruce\Programming\pipenv-example-basic> python --version
    Python 3.10.4
    ```

1. Verify `pip` is installed:  
`pip --version`  
Sample ouput:  
    ```
    PS C:\Users\Bruce\Programming\pipenv-example-basic> pip --version
    pip 22.1.1 from C:\Users\Bruce\AppData\Local\Programs\Python\Python310\lib\site-packages\pip (python 3.10)
    ```

1. Check currently installed packages:  
`pip list`  
Sample output:  
    ```
    PS C:\Users\Bruce\Programming\pipenv-example-basic> pip list
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
    PS C:\Users\Bruce\Programming> pip install --user pipenv
    Collecting pipenv
      Downloading pipenv-2022.5.2-py2.py3-none-any.whl (3.9 MB)
        ---------------------------------------- 3.9/3.9 MB 14.8 MB/s eta 0:00:00
    Collecting virtualenv
      Downloading virtualenv-20.14.1-py2.py3-none-any.whl (8.8 MB)
        ---------------------------------------- 8.8/8.8 MB 26.7 MB/s eta 0:00:00
    Requirement already satisfied: setuptools>=36.2.1 in c:\users\bruce\appdata\local\programs\python\python310\lib\site-packages (from pipenv) (58.1.0)
    Collecting virtualenv-clone>=0.2.5
      Downloading virtualenv_clone-0.5.7-py3-none-any.whl (6.6 kB)
    Requirement already satisfied: pip>=22.0.4 in c:\users\bruce\appdata\local\programs\python\python310\lib\site-packages (from pipenv) (22.1.1)
    Collecting certifi
      Downloading certifi-2022.5.18.1-py3-none-any.whl (155 kB)
        ---------------------------------------- 155.2/155.2 kB ? eta 0:00:00
    Collecting six<2,>=1.9.0
      Downloading six-1.16.0-py2.py3-none-any.whl (11 kB)
    Collecting distlib<1,>=0.3.1
      Downloading distlib-0.3.4-py2.py3-none-any.whl (461 kB)
        ---------------------------------------- 461.2/461.2 kB 30.1 MB/s eta 0:00:00
    Collecting filelock<4,>=3.2
      Downloading filelock-3.7.0-py3-none-any.whl (10 kB)
    Collecting platformdirs<3,>=2
      Downloading platformdirs-2.5.2-py3-none-any.whl (14 kB)
    Installing collected packages: distlib, virtualenv-clone, six, platformdirs, filelock, certifi, virtualenv, pipenv
      WARNING: The script virtualenv-clone.exe is installed in 'C:\Users\Bruce\AppData\Roaming\Python\Python310\Scripts' which is not on PATH.
      Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
      WARNING: The script virtualenv.exe is installed in 'C:\Users\Bruce\AppData\Roaming\Python\Python310\Scripts' which is not on PATH.
      Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
      WARNING: The scripts pipenv-resolver.exe and pipenv.exe are installed in 'C:\Users\Bruce\AppData\Roaming\Python\Python310\Scripts' which is not on PATH.
      Consider adding this directory to PATH or, if you prefer to suppress this warning, use --no-warn-script-location.
    Successfully installed certifi-2022.5.18.1 distlib-0.3.4 filelock-3.7.0 pipenv-2022.5.2 platformdirs-2.5.2 six-1.16.0 virtualenv-20.14.1 virtualenv-clone-0.5.7
    ```

1. Note the 'WARNINGS's in output and copy the `Scripts` location provided:  
Sample location:  
`C:\Users\Bruce\AppData\Roaming\Python\Python310\Scripts`  

1. Add location of this specific `Scripts` directory `C:\Users\Bruce\AppData\Roaming\Python\Python310\Scripts` to user `PATH` variable:  
    * Press "Windows Key", then search for "path", then choose "Edit the system environment variables":  
        ![edit_system_environment_variables_choice](https://user-images.githubusercontent.com/47562501/171073588-e1dfd184-8042-43ed-9b30-27beafdfb606.png)

    * Choose "Environment Variables" button near bottom right:  
        ![environment_variables_button](https://user-images.githubusercontent.com/47562501/171073881-fb22f821-bd32-405a-8e51-75faa7338257.png)

    * Double click "Path" line in "User variables for User":  
        ![click_path_variable](https://user-images.githubusercontent.com/47562501/171073998-80740273-66c4-4ebc-b895-ae656ff73e03.png)

    * Click the "New" button:  
        ![click_the_new_button](https://user-images.githubusercontent.com/47562501/171074517-7a4e9b5d-06c7-45ee-90f9-aca9c286c3d0.png)

    * Paste the absolute route copied previously into the new line:  
        ![add_scripts_directory_location_to_path](https://user-images.githubusercontent.com/47562501/171074613-4289709a-4a33-445f-bf44-d2280b87ccbe.png)

    * Click "OK" to save changes and close "Edit environment variable" page:  
        ![click_ok_to_save_path](https://user-images.githubusercontent.com/47562501/171074756-ff56234e-676d-4f80-ad7e-54674f2da804.png)

    * Click 'OK' to close "Environment variables" page:  
        ![click_ok_to_close_environment_variables_page](https://user-images.githubusercontent.com/47562501/171074909-f2644c51-66f8-4468-b477-b95d2dcd1bb6.png)

    * Click 'OK' to close "System Properties" page:  
        ![click_ok_to_close_system_properties_page](https://user-images.githubusercontent.com/47562501/171074951-3b232a6c-aca7-449c-aa37-3a0dbdf20a2b.png)

1. Verify `pipenv` install:  
`pipenv --version`  
Sample output:  
    Note: This notification is received since we added a new item to "PATH" and that change is not available to the current terminal session. So we start a new terminal session.
    ```
    PS C:\Users\Bruce\Programming> pipenv --version
    pipenv: The term 'pipenv' is not recognized as a name of a cmdlet, function, script file, or executable program.
    Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
    ```

1. Start new terminal session.

1. Verify `pipenv` is installed:  
`pipenv --version`  
Sample output:  
    ```
    PS C:\Users\Bruce\Programming> pipenv --version
    pipenv, version 2022.5.2
    ```

1. Check new currently installed packages:
  Note: We have about eight new packages installed due to installation of `pipenv`.  
`pip list`  
Sample output:  
    ```
    PS C:\Users\Bruce\Programming> pip list
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

1. Continue and [Create `pipenv` virtual environment](create_pipenv_virtual_environment.md) or go back to [README.md](../README.md).
