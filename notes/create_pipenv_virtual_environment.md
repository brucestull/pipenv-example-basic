# Create `pipenv` Virtual Environment

## TL;DR:
* In a terminal session in project root:  
`pipenv install`  

## Prepare (things to check before creating virtual environment):

1. Ensure our current terminal session is in same directory as `Pipfile` and `Pipfile.lock`, typically this is the root of the project repository.

1. Investigate current directory contents:  
`ls`  
Pertinent directory contents (we have a git repository directory which contains a `notes` directory):
    ```
    PS C:\Users\Bruce\Programming\pipenv-example-basic> ls

        Directory: C:\Users\Bruce\Programming\pipenv-example-basic

    Mode                 LastWriteTime         Length Name
    ----                 -------------         ------ ----
    d----           5/30/2022 10:12 PM                notes
    -a---           5/29/2022  6:40 PM           1455 .gitignore
    -a---           5/30/2022 10:18 PM            503 README.md
    ```

1. Verify current installed packages (we want to make sure we have `pipenv` installed). Also, these are the globally installed packages:  
`pip list`  
Sample output:
    ```
    PS C:\Users\Bruce\Programming\pipenv-example-basic> pip list
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

1. Verify, using PowerShell, that current `python.exe` used is global. By 'global' I mean that it is not in an existing virtual environment. The `python.exe` is located in a default installation location. We will see below that the current `python.exe` will be a different installation when we are using the virtual environment:  
`Get-Command python | fl *`  
Sample output:
    ```
    PS C:\Users\Bruce\Programming\pipenv-example-basic> Get-Command python | fl *

    HelpUri            :
    FileVersionInfo    : File:             C:\Users\Bruce\AppData\Local\Programs\Python\Python310\python.exe
                        InternalName:     Python Console
                        OriginalFilename: python.exe
                        FileVersion:      3.10.4
                        FileDescription:  Python
                        Product:          Python
                        ProductVersion:   3.10.4
                        Debug:            False
                        Patched:          False
                        PreRelease:       False
                        PrivateBuild:     False
                        SpecialBuild:     False
                        Language:         Language Neutral

    Path               : C:\Users\Bruce\AppData\Local\Programs\Python\Python310\python.exe
    Extension          : .exe
    Definition         : C:\Users\Bruce\AppData\Local\Programs\Python\Python310\python.exe
    Source             : C:\Users\Bruce\AppData\Local\Programs\Python\Python310\python.exe
    Version            : 3.10.4150.1013
    Visibility         : Public
    OutputType         : {System.String}
    Name               : python.exe
    CommandType        : Application
    ModuleName         :
    Module             :
    RemotingCapability : PowerShell
    Parameters         :
    ParameterSets      :
    ```

## Process:

1. Create `pipenv` virtual environment:  
`pipenv install`  
Sample output:
    ```
    PS C:\Users\Bruce\Programming\pipenv-example-basic> pipenv install
    Creating a virtualenv for this project...
    Pipfile: C:\Users\Bruce\Programming\pipenv-example-basic\Pipfile
    Using C:/Users/Bruce/AppData/Local/Programs/Python/Python310/python.exe (3.10.4) to create virtualenv...
    [=   ] Creating virtual environment...created virtual environment CPython3.10.4.final.0-64 in 3706ms
    creator CPython3Windows(dest=C:\Users\Bruce\.virtualenvs\pipenv-example-basic-UBKsikLo, clear=False, no_vcs_ignore=False, global=False)
    seeder FromAppData(download=False, pip=bundle, setuptools=bundle, wheel=bundle, via=copy, app_data_dir=C:\Users\Bruce\AppData\Local\pypa\virtualenv)
        added seed packages: pip==22.0.4, setuptools==62.1.0, wheel==0.37.1
    activators BashActivator,BatchActivator,FishActivator,NushellActivator,PowerShellActivator,PythonActivator

    Successfully created virtual environment!
    Virtualenv location: C:\Users\Bruce\.virtualenvs\pipenv-example-basic-UBKsikLo
    Creating a Pipfile for this project...
    Pipfile.lock not found, creating...
    Locking [dev-packages] dependencies...
    Locking [packages] dependencies...
    Updated Pipfile.lock (e4eef2)!
    Installing dependencies from Pipfile.lock (e4eef2)...
    ================================ 0/0 - 00:00:00
    To activate this project's virtualenv, run pipenv shell.
    Alternatively, run a command inside the virtualenv with pipenv run.
    ```

1. Note line with "Virtualenv location:", this is the location of our virtual environment. `pipenv install` will create a virtual environment directory which has the project directory name followed by a dash and then a unique string.  
Note: The location of the virtual environment is not the same as the location of the code we will create for our project.  
Sample line:
    ```
    Virtualenv location: C:\Users\Bruce\.virtualenvs\pipenv-example-basic-UBKsikLo
    ```

1. Inspect current directory contents. Note presense of two new files: `Pipfile` and `Pipfile.lock`. These are the files which contain the `pipenv` configuration details for the project:  
`ls`  
Sample output:
    ```
    PS C:\Users\Bruce\Programming\pipenv-example-basic> ls

        Directory: C:\Users\Bruce\Programming\pipenv-example-basic

    Mode                 LastWriteTime         Length Name
    ----                 -------------         ------ ----
    d----           5/30/2022 10:12 PM                notes
    -a---           5/29/2022  6:40 PM           1455 .gitignore
    -a---           5/30/2022 10:30 PM            139 Pipfile
    -a---           5/30/2022 10:30 PM            454 Pipfile.lock
    -a---           5/30/2022 10:18 PM            503 README.md
    ```

1. Activate the virtual environment so we can investigate it:  
`pipenv shell`  
Sample output:
    ```
    PS C:\Users\Bruce\Programming\pipenv-example-basic> pipenv shell
    Launching subshell in virtual environment...
    PowerShell 7.2.4
    Copyright (c) Microsoft Corporation.

    https://aka.ms/powershell
    Type 'help' to get help.
    ```

1. Investigate the installed packages of our virtual environment and note that they are different than those listed in global environment above:  
`pip list`  
Sample output:
    ```
    PS C:\Users\Bruce\Programming\pipenv-example-basic> pip list
    Package    Version
    ---------- -------
    pip        22.0.4
    setuptools 62.1.0
    wheel      0.37.1
    ```

1. We can check, using PowerShell command, which python installation we are using in our virtual environment:  
Note: The `python.exe` is located in our virtual environment, which is different than the global install noted above.  
`Get-Command python | fl *`  
Sample output:
    ```
    PS C:\Users\Bruce\Programming\pipenv-example-basic> Get-Command python | fl *

    HelpUri            :
    FileVersionInfo    : File:             C:\Users\Bruce\.virtualenvs\pipenv-example-basic-UBKsikLo\Scripts\python.exe
                        InternalName:     Python Launcher
                        OriginalFilename: py.exe
                        FileVersion:      3.10.4
                        FileDescription:  Python
                        Product:          Python
                        ProductVersion:   3.10.4
                        Debug:            False
                        Patched:          False
                        PreRelease:       False
                        PrivateBuild:     False
                        SpecialBuild:     False
                        Language:         Language Neutral

    Path               : C:\Users\Bruce\.virtualenvs\pipenv-example-basic-UBKsikLo\Scripts\python.exe
    Extension          : .exe
    Definition         : C:\Users\Bruce\.virtualenvs\pipenv-example-basic-UBKsikLo\Scripts\python.exe
    Source             : C:\Users\Bruce\.virtualenvs\pipenv-example-basic-UBKsikLo\Scripts\python.exe
    Version            : 3.10.4150.1013
    Visibility         : Public
    OutputType         : {System.String}
    Name               : python.exe
    CommandType        : Application
    ModuleName         :
    Module             :
    RemotingCapability : PowerShell
    Parameters         :
    ParameterSets      :
    ```

1. We haven't installed any project specific packages.  
    * We will now use `pipenv install PACKAGE` or `pipenv install PACKAGE==VERSION` to install any new packages so that `Pipfile` will automagically track and update packages and any desired specific versions.

## Summary:
* After following the previous steps, the user should have a `pipenv` virtual environment set up for their project:
    * `pipenv` configuration files `Pipfile` and `Pipfile.lock` in project root.  
    `ls`  
    Sample output:  
        ```
        PS C:\Users\Bruce\Programming\pipenv-example-basic> ls

            Directory: C:\Users\Bruce\Programming\pipenv-example-basic

        Mode                 LastWriteTime         Length Name
        ----                 -------------         ------ ----
        d----          2022-05-30    22:44                notes
        -a---          2022-05-29    03:59           1455 .gitignore
        -a---          2022-05-30    22:44            150 Pipfile
        -a---          2022-05-30    22:44            474 Pipfile.lock
        -a---          2022-06-01    10:41            997 README.md
        ```
    * `pipenv` virtual environment created somewhere on their system:  
    Sample location:  
        ```
        C:\Users\Bruce\.virtualenvs\pipenv-example-basic-UBKsikLo
        ```

[README.md](../README.md)