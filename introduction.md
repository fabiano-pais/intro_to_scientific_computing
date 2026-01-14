---
title: "Everything you need to know before getting started"
teaching: 10 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions

- What is scientific computing?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Are you familiar with programming languages?
- Do you have experience with command-line applications?

::::::::::::::::::::::::::::::::::::::::::::::::

## Setting the stage

Scientific computing is all about solving problems using computers. The complexity of the problem might require proficiency in one or more programing languages. You may need to be able to write Python or R scripts at some point, but you'll definetly need to know BASH for a start. BASH is a very simple programming language, or a shell actually, and one that can connect you to a high performance computer (HPC).
In order to learn BASH, you'll need to work with a command-line application, such as a terminal, to get the most from BASH.

Here, you'll learn the most important commands in BASH so you can carry on your jobs. This will be achieved by working through a series of exercises using a terminal within Google Colab as the main interface.  You'll be given instructions on how to open a terminal within Google Colab at the next episode. However, if you don't have a Google account yet, please create one before continuing.

::::::::::::::::::::::::::::::::::::: callout

Do you know what is a Terminal, a Shell and BASH?

We provide a few basic definitions to the above, but we reconmend reading additional documentation (widely available online).

::::::::::::::::::::::::::::::::::::::::::::::::

## Terminal

It's a program that allows you to communicate with your computer throught a commnand-line environment. So, basically, you'll interact with the computer only by entering commands to perform specific tasks. It's mainly operated throughout the keyboard, altough there are Terminals that provide a small interaction with the mouse.

Although most Operating Systems (OS) provide beatifull graphical user interfaces (GUIs), Terminals are still widely used by programmers and data scientists. Terminals are very powerfull, and once you get used to them, you'll be able to perform tasks much faster than using a GUI. If you need to access a remote machine, i.e. an HPC, you will mostlikely do it using a Terminal. HPCs can provide users with more computer cores and memory for performing advanced tasks for complex data analysis.

Many Terminals are availables for each OS. We strongly suggest VSCode (https://code.visualstudio.com), which is freely available to all OS. Yoy may also like Warp (https://www.warp.dev/j).



## Shell

Shell is a part of the software that interprets the commands entered via the keyboard. BASH is (probably) the most popular Shell, but there are others, such as ZSH and PowerShell. You can switch between Shells, but you need to be aware that some commands may differ slightly between them. Confirguration files are also different, and therefore cannot just been shared between them. Shells that are POSIX-compliant (such as BASH and ZSH) share a lot of similarities, so most commands will work in both shells. PowerShell is not POSIX compliant, but it's still widely used.

::::::::::::::::::::::::::::::::::::: challenge 

## Challenge 1: Can you link the Shells bellow to its native Operating System?

Each the following Operating Systems has an embeded main shell

MacOS, Linux, Windows.

Which is the main Shell for each?

:::::::::::::::::::::::: solution

## Output

ZSH is the main MacOS shell;
BASH is the main one for Linux;
PowerShell is the Windows main shell.

::::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

## BASH

BASH was developed by Brian Fox in 1988, and first released in 1989. Like any programming language, it can be used to automate tasks, and that's a powerfull thing. Since it was one of the first programming languages ported by Linus Torvalds to Linux, it has become the default shell on most Linux distributions.
BASH supports a wide range of functionalities, such as using variables and arrays as data structures. By default, BASH reads user code one line at a time, but it can also read scripts containing multiple lines of code. BASH scripts are plain text files with a `.sh` extension that can be executed in the terminal in a non-interactive way and whithout user intervention.

::::::::::::::::::::::::::::::::::::: callout

## Swithing between Shells

It's entirely possible to swith between different shells. For example, if you are using ZSH and want to switch to BASH on a macOS, you can simply type `bash` in the terminal. To return to ZSH, type `zsh`. There are other shells available, such as `fish`(https://fishshell.com) for example. Fish is not POSIX compliant, but it has a lot of user-friendly features and it's quite similar to BASH. 

::::::::::::::::::::::::::::::::::::::::::::::::

[r-markdown]: https://rmarkdown.rstudio.com/
