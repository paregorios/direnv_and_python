# direnv and python for macOS

1. Install [direnv](https://direnv.net/) and [pyenv](https://github.com/pyenv/pyenv). I use [homebrew](https://brew.sh/) for these tasks. There may be setup and/or shell integration steps for these tools that I'm omitting (I can't remember), so check their docs.
2. Determine the python version(s) you will likely be using and install them with `pyenv` at the command line (i.e., in Terminal). 
    - `pyenv versions` will show you the versions already locally installed.
    - `pyenv install --list` will show you all the versions __available__ to install.
    - `pyenv install 3.12.4` will install that particular version for use on your local system.
3. Using the Terminal, move to or create and move to a directory that will contain your python project (package or script or whatever).
4. Configure the directory using `direnv`. To specify the python version you want to use as the virtual environment for python work in that directory (and its children), create a `.envrc` file and put the line `layout pyenv 3.12.5` (or whatever python version you need) and save the file.
5. Follow the `direnv` prompt at the command line to "Run `direnv allow` to approve its content."
6. The first time you do this, `direnv` will invoke `pyenv` to set up a python virtual environment inside a `.direnv` subfolder it creates for this purpose. 
7. Subsequently, when you `cd` into this directory, `direnv` will activate the virtual environment. When you `cd` out of this directory, `direnv` will deactivate the virtual environment.
8. When in the directory with the virtual environment activated, you can add packages and do updates in the normal ways, e.g., `pip install -U pip`. 
9. Recent versions of Visual Studio Code correctly detect and use your `direnv`-managed virtual environment if started from the command line in the directory using `code .`. 
