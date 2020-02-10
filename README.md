# Installing Python on your Windows 64 bit machine

Run this to install python on your PC, 64 bit. To check if you already have python installed, see [this](https://www.wikihow.com/Check-Python-Version-on-PC-or-Mac) link. 

It is likely that you already have python installed. If you end up multiple "pythons" installed on your computer, telling the computer where to look for python packages may be tricky - so it's best to just have one single python, and I recommend Miniconda3.

If you already have Anaconda3 already installed and you wish to continue with this tutorial, navigate to ProgramData/Anaconda3 and run the uninstall .exe file.

## Step 1

Please make a folder called `code` under this path, using your username: `/Users/my_user_name/Documents/code`. This is where we'll keep our repositories, such as `ocpi-lab-automation`. 

Download these:
- [miniconda3 for python3 64 bits](https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe). Barebones python, similar to Anaconda, but without the extra packages.
- [GIT for windows](https://gitforwindows.org/). This is a file version management system. Comes with gitbash command prompt.
- [Pycharm](https://www.jetbrains.com/pycharm/download/download-thanks.html?platform=windows&code=PCC). This is a visual interface for using python, similar to Spyder.
- `pip` is used to install most python packages, for instance `pip install numpy`. Right-click [this](https://bootstrap.pypa.io/get-pip.py) link and select save link as. Save this `get-pip.py` file under the `code` directory you just created above. 

## Step 2

Install python3 64 bits by running the miniconda3 .exe file. When prompted, make sure to check the box "Add Anaconda to the system PATH environment variable". 

## Step 3

Many python packages are installed using `make`and `Makefiles`. To do this, you can install `chocolatey`. Here's how: 

First, login to [GitHub](http://github.com/) (make sure you have made a Github account - with UCSB email, you can make a Pro version)

Next, open windows Command Prompt as administrator. You can do this by typing `cmd` in the windows search bar and right click to `Run as administrator`.

Finally, copy-paste this entire line into the terminal:

```
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

then run
```
choco install make
```

## Step 4

Now we will set up `pip`. This is a platform to easily install packages, example `pip install numpy` install numpy, a powerful math processing package.

First, open GitBash (or another command prompt). Type `python` and press enter. If Python is installed correctly, you should see output that says something like `python 3.7`. If you receive a message, `Python is not recognized as an internal or external command, operable program or batch file`, then Python is either not installed or the system variable path hasn’t been set. You’ll need to either launch Python from the folder in which it is installed or adjust your system variables to allow Python to be launched from any location. If you see this problem on GitBash, [this](https://stackoverflow.com/questions/22869192/git-bash-wont-run-my-python-files) link has a solution. If that doesn't work, follow the instructions [here](https://stackoverflow.com/questions/3701646/how-to-add-to-the-pythonpath-in-windows-so-it-finds-my-modules-packages) where you add the python path environment variable manually through Windows advanced system settings.

Next, navigate to the location of the `get-pip.py` file you downloaded above (e.g. `cd /yourpath`). Then run,

```
python get-pip.py
```

Pip is now installed! Now you can run `pip install numpy ` and other useful packages.


## Step 5

Now you have successfully installed python3 on your PC. You are ready to use a github repo such as `ocpi-lab-automation` by following the install steps for that repo page. If you would first like to start out by playing around with python, open PyCharm and select `New Project`. Make sure to create a new project using using an existing interpreter: Python 3.7 that is under ProgramData\Miniconda3.

![creating new project](https://github.com/ocpi-ucsb/install_python/blob/master/images/create_new_python_project.PNG)

You can also play around with python using [Jupyter](https://jupyter.org/). Jupyter offers notebooks that can run python. You evaluate pieces of code sequentially, similar to Mathematica. In our case, JupyterLab is probably of most use to us. For example, you can create a new JupyterLab notebook every day of running an experiment. The notebook tracks all of the commands you send to the experiment, effectively acting as a laboratory notebook that never misses anything. 

To install Jupyter lab, run
```
pip install jupyterlab
```

If you'd like to see the power of jupyterlab, check out [this](https://github.com/jupyter/jupyter/wiki/A-gallery-of-interesting-Jupyter-Notebooks) link.