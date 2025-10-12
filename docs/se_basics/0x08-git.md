# 0x08. Git
`Git`
`Code versioning`
`Github`

Most of the projects in this program are supposed to be done in a Linux (Ubuntu) environment.

For that matter, you will need to set up a similar environment for that purpose. This project is therefore a guide for you to set up the necessary coding environment irrespective
of the operating system that you are using.

## Resources
Resources to learn Git
About READMEs
How to write a Git commit message

## Resources for advanced tasks
Learning branching
Effective pull requests and other good practices for teams using GitHub

## Learning Objectives
- What is source code management
- What is Git
- What is GitHub
- What is the difference between Git and GitHub
- How to create a repository
- What is a README
- How to write good READMEs
- How to commit
- How to write helpful commit messages
- How to push code
- How to pull updates
- How to create a branch
- How to merge branches
- How to work as collaborators on a project
- Which files should and which files should not appear in your repo

## General Requirements
- A `README.md` file at the root of the `PyLAMP-zero_day` repo, containing a description of the repository
- A `README.md` file, at the root of the folder of this project (i.e. 0x08-git), describing what this project is about
- __Do not use GitHub’s web UI__, but the command line to perform the exercise (except for operations that can not possibly be done any other way than through the web UI). You won’t be able to perform many of the task requirements on the web UI, and you should start getting used to the command line for simple tasks because many complex tasks can only be done via the command line.
- Your answer files should only contain the command, and nothing else

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
__Step 0 - Create an account on GitHub [if you do not have one already]__

You will need a GitHub account for all your projects at the PyLAMP Program. If you do not already have a github.com account, you can create an account for free here.

__Step 1 - Create a Personal Access Token on Github__

To have access to your repositories and authenticate yourself, you need to create a Personal Access Token on Github.

You can follow [this tutorial]() to create a token.

Once it’s created, you should have a token that looks like this:

__Step 2 - Create your first repository__

Using the graphic interface on the [github website](), create your first repository.
- Name: `PyLAMP-zero_day`
- Description: `I'm now a PyLAMP Student, this is my first repository as a full-stack engineer`
- Public repo
- No `README`, `.gitignore`, or `license`

__Step 3 - Clone your repository__

On your ubuntu, do the following:
- Clone your repository

```
root@896cf839cf9a:/# git clone https://{YOUR_PERSONAL_TOKEN}@github.com/{YOUR_USERNAME}/PyLAMP-zero_day.git
Cloning into 'PyLAMP-zero_day'...
warning: You appear to have cloned an empty repository.
```
> __Replace {YOUR_PERSONAL_TOKEN} with your token from step 1__

> __Replace {YOUR_USERNAME} with your username from step 0 and 1__

__Step 4 - Create the README.md and push the modifications__

Navigate to this new directory. [Tips]()
```
root@896cf839cf9a:/# cd PyLAMP-zero_day/
root@896cf839cf9a:/PyLAMP-zero_day#
```

Create the file `README.md` with the content `My first readme`. [Tips]()
```
root@896cf839cf9a:/PyLAMP-zero_day# echo 'My first readme' > README.md
root@896cf839cf9a:/PyLAMP-zero_day# cat README.md
My first readme
```

Update your git identity
```
root@896cf839cf9a:/alx-pre_course# git config --global user.email "you@example.com"
root@896cf839cf9a:/alx-pre_course# git config --global user.name "Your Name"
```

Add this new file to git, commit the change with this message “My first commit” and push to the remote server / origin
```
root@896cf839cf9a:/PyLAMP-zero_day# git add .
root@896cf839cf9a:/PyLAMP-zero_day# git commit -m 'My first commit'
[master (root-commit) 98eef93] My first commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md
root@896cf839cf9a:/PyLAMP-zero_day# git push
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 212 bytes | 212.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/{YOUR_USERNAME}/PyLAMP-zero_day.git
 * [new branch]      master -> master
 ```

Good job!

You pushed your first file in your __first repository__ of the __first task__ of __your first PyLAMP Program__ project.

You can now check your repository on GitHub to see if everything is good.
Repo:
- GitHub repository: `PyLAMP-zero_day`
- File: `README.md`

<!-- ### 1. Hello Ubuntu
Inside the `zero_day` repo, create a new directory called `0x00-wsl`.
Add a `README.md` file to this directory.

On Ubuntu in your wsl. What does the command `uname` print when you run it without any option?

Type your answer into a file in the `0x00-wsl` directory and push it to `GitHub`. Name your file accordingly as shown below.

Repo:
- GitHub repository: `zero_day`
- Directory: `0x00-wsl`
- File: `0-hello_ubuntu` -->
