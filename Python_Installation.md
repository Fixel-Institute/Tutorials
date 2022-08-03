# Python Installation Tutorial

## Introduction

This tutorial mainly go through basic process to get Python 3 working on a computer. There are many ways of doing this, but this is mainly to offer a basic introduction for first time Python users. 

## Distributions

Python language can be installed directly via [official site](https://www.python.org/) or package distribution system but this is just to get the basic compiler up and running, and it is not the best option for first time Python users as it lacks many important features that other redistribution provide. 

One of the most popular distribution of Python is the [Anaconda Python](https://www.anaconda.com/products/distribution) distribution for Windows, MacOS, and Linux system. It is a one-package-for-all distrbution that include not only Python compiler, but also integrated-development-envrionment (IDE) such as Spyder 5 and Jupyter Notebook. In addition, many commonly used packages for scientific computing will be automatically installed, including Numpy, Scipy, Scikit-Learn, etc. 

## Anaconda Python

You can get Anaconda via their [official site](https://www.anaconda.com/products/distribution). A simple installer will be downloaded for Windows/MacOS/Linux. After installation, you can open the "Anaconda Navigator" program to launch available IDEs, including JupyterLab, Jupyter Notebook, Spyder 5, VS Code, and RStudio. 

### Package Installation

In Python, open-source tools can be installed via the PyPI commands (Python Package Index). Example code that install Numpy, Scipy, and Pandas package are like below:
```
pip install numpy scipy pandas
```

However, Anaconda also has its own Package system using the conda commands: 
```
conda install numpy scipy pandas
```

This is actually significantly better than PyPI on Windows. Most Python packages are being developed in a Linux environment, making compilation of some less-known packages on Windows often lead to errors. However, Anaconda has its own package system that store pre-compiled packages for each platform (Windows/MacOS) and ensure that if you get it via conda you will always be able to install that package.

* If you can't get it via conda, you may have to compile that on your own. But Anaconda has almost all packages ready for you.

### Virtual Environment

Generally speaking, virtual environment is not an essential tool for a general user. What a virutal environment does is that it create a standalone Python distribution in a local folder that you designated. Then you can install packages in that virtual environment and execute programs in that virtual environment without affecting the base Python distribution.  

It is a tool generally used to ensure the dependencies for a package is limited and controlled. For example, if you want to write a standalone software, but you want to make sure all packages required by the software are accounted for, you start the virutal environment before your core development and start adding packages needed one by one. After the development is completed, during distribution of the software, you can simply provide a one-line installation script that install all packages required but nothing else.

For example, here is a one-line installation for all packages required by the Percept Analysis Server. 
```
pip3 install django djangorestframework numpy scipy pandas spectrum mysqlclient requests websocket-client joblib
```

In addition, if a certain project require an extremely outdated software package, but your current python environment already contained a newer version needed by all other software. You can create a virtual environment for that specirfic project and install the outdated package just for that pipeline only without affecting other tools.

In Anaconda, you can create virtual environment via
```
conda create --name NAME_OF_VIRTUAL_ENVIRONMENT
```

or if you do it through standard Python, install virtualenv first then call it directly to create a folder

```
pip install virtualenv
virtualenv NAME_OF_VIRTUAL_ENVIRONMENT
```

After a virtual environment is created, you can activate it via
```
conda activate NAME_OF_VIRTUAL_ENVIRONMENT
```
or if you did it through virtualenv
```
source NAME_OF_VIRTUAL_ENVIRONMENT/bin/activate
```
