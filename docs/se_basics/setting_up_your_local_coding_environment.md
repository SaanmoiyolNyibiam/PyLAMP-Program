# Setting up your local coding environment
`DevOps`
`Virtual machine`

Most of the projects in this program are supposed to be done in a Linux (Ubuntu) environment.

For that matter, you will need to set up a similar environment for that purpose. This project is therefore a guide for you to set up the necessary coding environment irrespective
of the operating system that you are using.

## Guide to running Ubuntu on different operating systems

1. For __Windows__ You have __three__ options for running Ubuntu on Windows:

- WSL: `WSL (Windows Subsystem for Linux)` is a feature that allows you to run Linux distributions natively on Windows. WSL is the easiest option to set up and use, and it provides a good introduction to Ubuntu.

- Vagrant: `Vagrant` is a tool for creating and managing virtual machines. It is a good option if you need to run Ubuntu for development or testing purposes, as it allows you to create isolated environments that are easy to replicate and share.

- Docker: `Docker` is a tool for containerizing applications. It is a good option if you need to run Ubuntu for specific tasks, such as running a web server or database. But also remember using docker will need an installation of WSL.

2. For __macOS__ If you have:

- a Mac with an __Apple Silicon chip__, you can only use Docker to run `Ubuntu`.
- a Mac with an __Intel chip__, you can use `Vagrant` or `Docker`.

## Resources
- [Virtual Machine](https://en.wikipedia.org/wiki/Virtual_machine)
- [man uname](https://linux.die.net/man/1/uname)
- [Guide to install WSL and Ubuntu on Windows](https://learn.microsoft.com/en-us/windows/wsl/install)

## Learning Objectives
- What is a virtual machine
- What is Vagrant
- Who wrote Vagrant
- What is Ubuntu
- What does “Ubuntu” mean
- How to use VMs with Vagrant
- What does the command `uname` do

## General Requirements
- A `README.md` file at the root of the repo, containing a description of the repository.
- A `README.md` file, at the root of the folder of this project (i.e. `0x00-wsl`), describing what this project is about.

## More Info

### Install `git`
If `git` is not already installed on your terminal:
```
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install git
```

### Basic usage
At the end of this project you should be able to reproduce and understand these command lines:

```
$ git clone <repo>
$ touch test
$ git add test
$ git commit -m "Initial commit"
$ git push origin main
```

## Tasks

### 0. Create and setup your Git and GitHub account
- You will need Git for this project, you might have to [install it](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) on your computer if it’s not done yet.

- Configure your basic info (name, email) on your local machine – they will be part of your commits. [Tips](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)

On [GitHub.com](https://github.com/):

- You will need a GitHub account for this project.If you do not already have a github.com account, you can create an account for free [here](https://github.com/).

- Using the graphic interface on the website, create the repository (if it’s not done yet)
    - Description: `This is my first repository as a full-stack engineer`
    - Public repo: `zero_day`
    - No `README`, `.gitignore`, or `license`

On your computer, open a terminal and do the following:

- Navigate to your home directory. [Tips](https://linuxconfig.org/single-linux-command-to-return-to-home-directory)
- Create a directory `zero_day`. [Tips](https://help.ubuntu.com/community/Beginners/BashScripting)
- Navigate to this new directory. [Tips](https://askubuntu.com/questions/232442/how-do-i-navigate-between-directories-in-terminal)
- Initialize git and add the remote origin
- Create a file `README.md` with Vi (or other command line editors) and write a small [Markdown](https://wordpress.com/support/markdown-quick-reference/) text to present this project. __This file is mandatory in projects__
- Add this new file to git, commit the change with this message “My first commit” and push to the remote server / origin (Note: You will probably need to set your login/password to push to the remote server)
Good job!

You pushed your first file in your first repository of the first task of your first PyLAMP Program project.

Repo:

- GitHub repository: `zero_day`
- File: `README.md`

### 1. Hello Ubuntu
Inside the `zero_day` repo, create a new directory called `0x00-wsl`.
Add a `README.md` file to this directory.

On Ubuntu in your wsl. What does the command `uname` print when you run it without any option?

Type your answer into a file in the `0x00-wsl` directory and push it to `GitHub`. Name your file accordingly as shown below.

Repo:

- GitHub repository: `zero_day`
- Directory: `0x00-wsl`
- File: `0-hello_ubuntu`
