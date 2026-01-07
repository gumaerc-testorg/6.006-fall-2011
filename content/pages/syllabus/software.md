---
content_type: page
description: This section provides details on the programming environment for the
  course.
draft: false
learning_resource_types: []
ocw_type: CourseSection
parent_title: Syllabus
parent_type: CourseSection
parent_uid: f5734501-4b07-a46b-d16f-f4d95aef57d5
title: Software
uid: 439d0ff3-67dd-3140-f769-dbfd28c87874
video_metadata:
  youtube_id: null
---
This course makes use of Athena, MIT's UNIX-based computing environment. OCW does not provide access to this environment.

This section covers the 6.006 programming environment setup:

{{% resource_link "439d0ff3-67dd-3140-f769-dbfd28c87874" "CPython 2.7" "#cpython" %}}      
{{% resource_link "439d0ff3-67dd-3140-f769-dbfd28c87874" "PyPy" "#pypy" %}}      
{{% resource_link "439d0ff3-67dd-3140-f769-dbfd28c87874" "PIP" "#pip" %}}      
{{% resource_link "439d0ff3-67dd-3140-f769-dbfd28c87874" "IDEs / Code Editors" "#ide" %}}      
{{% resource_link "439d0ff3-67dd-3140-f769-dbfd28c87874" "PyDev in Aptana Studio" "#pydev" %}}

## Overview

In theory, you can solve all the 6.006 assignments with nothing other than Notepad. However, in order to be efficient and make the most out of the class, you’ll need a plethora of software, such as a Python interpreter, the PIP package manager, and an IDE. You can find this software on Athena, which is the only platform that we officially support. The rest of this document will help you set up this software on your own machine. We have provided instructions below for the following operating systems / distributions:

1. {{% resource_link "7df8be99-ef3a-4f75-bd63-3b3883558c0e" "Ubuntu Linux 11.04 or 11.10" %}}
2. Mac OS X 10.7 (Lion)
3. Windows 7

### Note on Windows Support

Windows is tricky to support because it does not obey standards such as POSIX out of the box, and we don’t use it for development. The course staff will attempt to help you with problems on Windows for the purpose of completing all the assignments, but please note that none of us use it on our own computers.

### Python

We will test your code against the CPython 2.7 and PyPy interpreters. Reasonable code should behave identically in CPython and PyPy, but we sometimes use PyPy for performance reasons. You should develop under CPython, and only use PyPy if some weird issue arises. This document walks you through installing both flavors.

## {{< anchor "cpython" >}}{{< /anchor >}}CPython 2.7

### Ubuntu Linux

Run the following command in a Terminal window:      
`sudo apt-get install -y python2.7 python-profiler`

Python 2.7 should now be installed. Run `python --version` to make sure that the version is 2.7.

### Mac OS X

We support the Python interpreter that comes with OS X 10.7 (Lion).

If you have OS X 10.6 (Snow Leopard), {{% resource_link "681ee1fc-5359-4d87-8858-224167184f11" "this Python 2.7.2 package (DMG)" %}} will most likely get you through the class, although the course staff will be unable to help you if you get stuck.

### Windows 7

1. Download {{% resource_link "5ef4c785-c194-40c8-8202-85a2e5f251a6" "Python 2.7.2 (MSI)" %}} and follow the wizard to install into the default location (C:\\Python27\\)
2. Add Python to the PATH
    1. Go to Start → Control Panel → System and Security → System
    2. On the left, click on Advanced system settings
    3. Make sure you’re on the Advanced tab, and click on the Environment Variables button
    4. In the top list, find the PATH entry and click on it. Then, click the Edit… button.
    5. Append the following to the end of the entry (semicolon, spacing, and quotes matter; use the folder where you installed Python instead if you didn’t use the default):      
        `;"C:\Python27"`
    6. If you had any open command prompt windows, close and reopen them so that they reflect the PATH change.

## {{< anchor "pypy" >}}{{< /anchor >}}PyPy

### Ubuntu Linux

1. Download a Linux binary from the {{% resource_link "e4e6e30f-e03e-4f2b-9c9e-379192e0133a" "PyPy download page" %}}.
2. Unpack it in the Downloads folder by double-clicking on the package.
3. Open a Terminal window, and type the following commands:
4. Install a required library:      
    `sudo apt-get install libssl0.9.8`
5. Move pypy to a different location:      
    `sudo mv ~/Downloads/pypy-1.6 /usr/local/pypy`
6. Make a symlink to pypy      
    `sudo ln -s /usr/local/pypy/bin/pypy /usr/local/bin/pypy`

You should now be able to run PyPy by typing `pypy`, unless you removed `/usr/local/bin` from your PATH.

### Mac OS X

1. Download {{% resource_link "3234384d-e6c4-4906-8176-592b27db3a34" "PyPy 1.6 for OS X (TAR)" %}}.
2. Unpack it in the Downloads folder by double-clicking on the package.
3. Open a Terminal window, and type the following commands:
4. Move PyPy to a different location:      
    `sudo mv ~/Downloads/pypy-1.6 /usr/local/pypy`
5. Make a symlink to pypy      
    `sudo ln -s /usr/local/pypy/bin/pypy /usr/local/bin/pypy`

You should now be able to run PyPy just type typing `pypy`, as `/usr/local/bin` should be in your PATH.

### Windows 7

1. Download {{% resource_link "83bd7a24-284a-416c-8c72-f61cc7bd7821" "PyPy 1.6 for Windows (EXE)" %}}.
2. Extract the zip file to C:\\pypy-1.6-win32-c
3. The main executable is C:\\pypy-1.6-win32-c\\pypy-c.exe

## {{< anchor "pip" >}}{{< /anchor >}}PIP

Make sure you have Python and PyPy installed before installing pip.

### Ubuntu Linux

You can test whether you were able to install pip for PyPy correctly by running `pypy-pip install pygments` and then running `pypy` and trying to import `pygments`. If it succeeds, and `pygments.__version__` looks like a version number, then you’ve installed PIP successfully. Do the same with pip for CPython by running `sudo pip install pygments` and then running python and trying to `import pygments`. Then check the pygments version again.

### Mac OS X

You can test whether you were able to install pip for PyPy correctly by running `pypy-pip install pygments` and then running `pypy` and trying to `import pygments`. If it succeeds, and `pygments.__version__` looks like a version number, then you’ve installed PIP successfully. Do the same with pip for CPython by running `pip install pygments` and then running `python` and trying to `import pygments`. Then check the pygments version again.

### Windows 7

1. Download and install {{% resource_link "501875cf-6a65-4786-802a-041c8c746674" "setuptools for Python 2.7" %}}.
2. Add the Scripts folder to the PATH
    1. Go to Start → Control Panel → System and Security → System
    2. On the left, click on Advanced system settings
    3. Make sure you’re on the Advanced tab, and click on the Environment Variables button
    4. In the top list, find the PATH entry and click on it. Then, click the Edit… button.
    5. Append the following to the end of the entry (semicolon, spacing, and quotes matter; use the folder where you installed Python instead if you didn’t use the default):      
        `;"C:\Python27\Scripts"`
    6. If you had any open command prompt windows, close and reopen them so that they reflect the PATH change.

Open a new command prompt window and type `easy_install pip`      
If this step fails, make sure you edited the PATH correctly in the previous step. For some students, leaving out the quotes (i.e. adding `;C:\Python27\Scripts` to the PATH) worked better.

pip should now be installed for CPython. You can test it by opening a command prompt window and running `pip install pygments`, then running `python` and checking that `import pygments` doesn’t fail and that `pygments.__version__` looks like a version number.

Now, install pip for PyPy:

1. Download these two files to C:\\pypy-1.6-win32-c\\pypy-1.6 (or wherever else you installed PyPy). If they open in your browser, you can typically go to the File menu and choose Save File As… to save them to your desired location (in this case, the PyPy folder).      
    {{% resource_link "ce25e356-3356-4137-9d4c-18634fc05103" "Get distribute\_setup.py" %}}      
    {{% resource_link "0c16a921-9d7e-4d08-9886-1289c16741d0" "Get get-pip.py" %}}
2. Open a new command prompt window, and change directories to your PyPy folder:      
    `cd C:\pypy-1.6-win32-c\pypy-1.6`
3. Run the following commands to install pip for PyPy:      
    `pypy-c distribute_setup.py`     
    `pypy-c get-pip.py`

pip should now be installed for PyPy in C:\\pypy-1.6-win32-c\\pypy-1.6\\bin. You can test it by opening a command prompt window and running `C:\pypy-1.6-win32-c\pypy-1.6\bin\pip install pygments`, then running `C:\pypy-1.6-win32-c\pypy-1.6\pypy-c` and checking that `import pygments` doesn’t fail and that `pygments.__version__` looks like a version number.

## {{< anchor "ide" >}}{{< /anchor >}}IDEs / Code Editors

An IDE (Integrated Development Environment) can help you develop Python programs more efficiently.

IDLE comes with Python, and is a good default choice. IDLE is installed by default on Windows and Mac OS X. On Ubuntu, you can install it with the following command: sudo apt-get install idle

## {{< anchor "pydev" >}}{{< /anchor >}}PyDev in Aptana Studio

### Ubuntu Linux

1. Launch Software Sources from the Ubuntu Menu. Select the Other Software tab, then select the Canonical Partners repositories. Close the dialog when done.
2. Open a Terminal window.
3. Update your software cache.      
    `sudo apt-get update`
4. Install the prerequisite software.      
    `sudo apt-get install -y sun-java6-jdk sun-java6-fonts ant ant-optional`     
    `libglade2-0 libgnome2-0 libgnomecanvas2-0 libgnomecanvas2-common`     
    `libgnomeui-0 libgnomeui-common sat4j git`
5. {{% resource_link "1db4d865-11a1-4048-a7c0-9b091f6e94f6" "Download Aptana Studio" %}} and extract it in your home directory.

### Mac OS X

{{% resource_link "1db4d865-11a1-4048-a7c0-9b091f6e94f6" "Download and install Aptana Studio" %}}.

### Windows

1. Download the latest version of the {{% resource_link "e1602486-1767-43c8-bd40-ad6f291ff194" "Java SE 6 JDK" %}}.
2. {{% resource_link "1db4d865-11a1-4048-a7c0-9b091f6e94f6" "Download and install Aptana Studio" %}}.