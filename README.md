# DS Unit 3 Onboarding

Please complete the following sections of this document before the beginning of our first Guided Project: 

- Text Editor - VS Code
- Command-Line Application
- Programming Language
- Virtual Environment Manager

The section about Git and setting up SSH keys can be completed *after* our first Guided Project if necessary. You will need to complete that section in order to attempt the stretch goal associated with the first assignment. 

## Text Editor - VS Code

To edit Python files locally, we'll need a development-class text editor. Students who don't already have a preferred editor or IDE are encouraged to [download and install VS Code](https://code.visualstudio.com/download).

On the download page for VS Code please make sure you select the application that is most appropriate for your operating system. For Mac users who have a machine with "Apple Silicon" aka the new M1 chip, please make sure that you download the Apple Silicon version by clicking the small button beneath the general MacOS installer. 

![Mac VS Code Download Buttons](/images/vs_code_download_mac.png)

For Mac users this process will result in a .zip file being downloaded to your machine. Double clicking on this file will reveal the VS Code application. You will need to manually click and drag the application into your applications folder to be able open VS Code through LaunchPad or Spotlight Search.

For Windows users this process will result in a .exe file being downloaded to your machine. Double clicking on this file will start up a graphical installer. Please follow the steps of the staller to complete installation.

> OPTIONAL: you may also want to further [customize your text editor's appearance and functionality](https://github.com/prof-rossetti/intro-to-python/blob/master/notes/devtools/vs-code.md#basic-configuration), as desired.

### Basic Configuration

After you have downloaded VS Code, you'll want to take some time to familiarize yourself with its [settings](https://code.visualstudio.com/docs/getstarted/settings) and menus.

The Command Pallete (accessible by typing "command + shift + P" for mac users and "control + shift + P" for windows users) is perhaps the biggest time-saving shortcut, and is worth exploring.

## Command-Line Application

To run Python files locally, we'll need a command-line application. A command line application is a tool for typing out written commands to interact with our computer rather than clicking through folders and menus with our mouse. Command-line applications have a steep learning curve but are necessary in order to use the tools that we will be learing during this unit.

Mac users who don't already have a preferred command-line application are encouraged to use the built-in Terminal application (no need to download anything).

Windows users who don't already have a preferred command-line application are encouraged to [download and install Git Bash](https://git-scm.com/downloads), which will integrate well with the other development tools and allow Windows users to write the same commands as Mac users. 

During the installation process when you reach the screen "Choosing the default editor used by Git" please select "Use Visual Studio Code as Git's default editor". If you forget and click through this step that's totally fine. It's rare that we make edits to files directly from Git Bash, but if you choose to do so, the the default editor is Vim which is notoriously confusing for beginners and has a very steep learning curve. Besides that setting, you can pretty much click through the recommended defaults to complete the installation process.

Ultimately, Windows users may opt to use an alternative tool such as the Command Prompt or Anaconda Prompt, but if you do you are responsible for translating unix-style commands you'll see everywhere to windows-style commands. 

> OPTIONAL (for Mac users): you may want to [customize your Terminal appearance and functionality](https://github.com/prof-rossetti/intro-to-python/blob/master/exercises/command-line-computing/mac-terminal-config.md), as desired.

> NOTE: newer Macs may use the "zsh" shell instead of the "bash" shell, in which case you can do the "\~/.bash_profile" customizations using a file like "\~/.zshrc" instead.

## Programming Language

To get started with Python locally, if you haven't already done so as instructed during Unit 2, you'll want to [download and install Anaconda](https://www.anaconda.com/distribution/), which will provide the ability to install and manage local installations of Python and third-party Python packages.

> IMPORTANT NOTE: please check the "add to PATH" option during installation, especially on Windows, so Anaconda will integrate with the other local development tools, such as Git Bash on Windows.

![Add to Path](/images/path.png)

> FYI: this installation process can take a half-hour or more, so prefer to do it over a strong Internet connection.

After installing Anaconda, you'll have access to the Python language and its side-kick, the Pip package manager. For more information on Python, see this bonus [`python` reference document](https://github.com/prof-rossetti/intro-to-python/blob/master/notes/clis/python.md). For more information on Pip, see this bonus [`pip` reference document](https://github.com/prof-rossetti/intro-to-python/blob/master/notes/clis/pip.md).

## Virtual Environment Manager

For reasons we'll discuss, it is a best practice to work on project-specific environments which have project-specific versions of the Python programming language and third-party Python packages. There are two main tools to help us do this.

The first alternative, which you may be using almost exclusively in other units, is the aforementioned Anaconda, which provides the `conda` utility. It is good to be familiar with using `conda` virtual environments. For more information on Anaconda, see this bonus [`conda` reference document](https://github.com/prof-rossetti/intro-to-python/blob/master/notes/clis/conda.md).

> NOTE: when using `conda` to activate a virtual environment for the first time, when prompted to do so, Git Bash users on Windows may need to run `conda init bash` and Zsh users on Mac may need to run `conda init zsh`.

The second alternative, which we'll be using almost exclusively in this unit, is [Pipenv](https://pipenv-fork.readthedocs.io/en/latest/). For more information on Pipenv, see this bonus [`pipenv` reference document](https://github.com/prof-rossetti/intro-to-python/blob/master/notes/python/packages/pipenv.md). Installation guidance:

Mac users are encouraged to download Pipenv via [homebrew](https://github.com/prof-rossetti/intro-to-python/blob/master/notes/clis/brew.md) (`brew install pipenv`). NOTE: Homebrew is a popular and amazing programmatic installation tool that no Mac developer should go without!

For Windows users, the process is more involved. First run `pip install --user pipenv` in Git Bash. If you have pip installed correctly you will see the following:

![pip install --user pipenv](/images/pipenv_installation.png
)

The warning here does need to be addressed before pipenv will work properly. You can even try running `pipenv -h` in the command line to see if pipenv is recognized as a command, if it is not recognized as a command then you need to do the following steps to update your `PATH` environment variable.

1. Use the search bar in the botton-left of the screen to search for "env" and then click "Edit the system environment variables"

![edit environmental variables windows](/images/env_search.png)

2. In the System Properties window click on the "Environment Variables..." button

![System Properties edit environmen variables button](/images/system_properties.png)

3. In the lower "System variables" section find the variable labelled `PATH`. Select it and then click the "Edit..." button.

![Edit PATH System Variable](/images/system_variables.png)

4. On the final screen click the "New" button and add the following two filepaths as new environment variables:

`C:\Users\<username>\AppData\Roaming\Python\Python38\Scripts`

`c:\Users\<username>\AppData\Roaming\Python\Python38\Site-Packages`

Replace `<username>` in the path with your usename. Also, please note the lowercase `c` in the second filepath. I'm not sure if it really matters, but mine didn't work until I made it lowercase. :shrugs:

![Path Variables for Pipenv](/images/path_variables.png)

Click "OK" to save your changes. Then, make sure you restart Git Bash. After you have restarted Git Bash, check to see if pipenv is now recognized by running the command `pipenv -h`

## Version Control Utility 

### GitHub Account

(Not required for the Module 1 Guided Project)

Finally, we need a version control utility to manage different versions of our software files, and interface with GitHub, where we can share our code and collaborate with others.

Unless you already have one, please take a moment to [create a GitHub account](https://github.com/) and if you haven't already, consider redeeming your [GitHub Student Developer Pack](https://education.github.com/pack), which provides some free resources. 

To access your Student Developer pack and verify that you are a BloomTech student, please go to <https://dashboards.bloomtech.com/> and click on the profile picture area in the top right corner, and then from the dropdown menu select "My GitHub." 

![My GitHub - Student Developer Pack](/images/my_github.png)

You may be prompted to log in to your GitHub account if you're not already. Then click "Get the GitHub Student Developer Pack" to redeem a whole bunch of cool offers and discounts. 

### <a name="ssh">Authenticating with GitHub</a>

Recently GitHub has discontinued its support of accessing repositories via https (which used to be the easiest way of authenticating with a repository). We now recommend that all students set up a SSH key and add it to their GitHub account in order to access repositories via SSH. SSH keys are device specific so you might need to do this once for each decide that you're going to want to access repositories from.

[Generating a new SSH key and adding it to the ssh-agent](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

[Adding a new SSH key to your GitHub account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

### Git CLI (Command Line Interface) Installation

We'll ideally want to get comfortable using Git from the command line. Git is a tool that is separate from GitHub and is used for "tracking changes in any set of files, usually used for coordinating work among programmers collaboratively developing source code during software development." [Wikipedia - Git](https://en.wikipedia.org/wiki/Git). For more information on Git, see this bonus [`git` reference document](https://github.com/prof-rossetti/intro-to-python/blob/master/notes/clis/git.md). 

  + Windows users can leverage the aforementioned Git Bash application for this purpose (nothing else to install).
  + Mac users can download Git via homebrew (`brew install git`), or in many cases Git may already be installed on your computer.

Although you should really invest the time to become a Git command-line pro, students on either Mac or Windows who are less comfortable with the command-line may optionally start by using the [GitHub Desktop](https://desktop.github.com/) application as a temporary bridge solution which provides a graphical user interface (GUI) for performing Git version control operations. If doing so, students should [customize GitHub Desktop](https://github.com/prof-rossetti/intro-to-python/blob/master/notes/devtools/github-desktop.md#configuration) to recognize their preferred dev tools (e.g. VS Code as the preferred text editor, and Terminal or Git Bash as the preferred command-line utility.)

## Success Criteria

After installing and configuring these local development tools, you should be able run each of the following commands without error:

  + `conda --version`
  + `pipenv --version`
  + `git --version`
  + `code ~/Desktop` (Mac Terminal, Windows Git Bash) OR `code C:\Users\USERNAME\Desktop` (Windows other)

## Preparation Exercise

Finally, in order to become more comfortable with these tools and command-line computing in general, consider completing this optional [Command-line Computing Exercise](https://github.com/prof-rossetti/intro-to-python/tree/master/exercises/command-line-computing).

Good luck, drop questions in Slack if you need help, and see you in class!
