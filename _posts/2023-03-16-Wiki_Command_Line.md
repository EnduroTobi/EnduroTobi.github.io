---
title: Command Line Basics
date: 2023-06-07 19:50:00 +0100
categories: [Wiki, Basics]
tags: [command line, basics]
---

## Introduction

The command line is a way to interact directly with the operating system of the computer. You can do that with a CLI (_Command Line Interface_). For Windows OS you typically use **Command Prompt** or **PowerShell**, for MacOS or Linux the Bash application (_**B**ourne-**A**gainst **SH**ell_) is most common. With newer MacOS versions, the **Z Shell** or **Zsh** is the new default application.

## Cheat Sheet

| Command                              | Description                                                                                                                                                |
| :----------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------- |
| clear                                | Clear the command display                                                                                                                                  |
| ls                                   | List all contents of current directoy                                                                                                                      |
| ls -a                                | List all content including hidden files                                                                                                                    |
| ls -l                                | List all content in long format                                                                                                                            |
| ls -t                                | List all content by the time hey were last modified                                                                                                        |
| ls -alt                              | Combines all attributes                                                                                                                                    |
| pwd                                  | "print working directory" - outputs the current directory                                                                                                  |
| ~                                    | Home directory                                                                                                                                             |
| cd /home/user/                       | Change directory to /home/user/                                                                                                                            |
| cd ..                                | Change directory by moving up in the hirachy                                                                                                               |
| cd ../..                             | Move up to directories                                                                                                                                     |
| cd ../user                           | Move one directory up and one down                                                                                                                         |
| mkdir assets                         | Create a directory called "assets"                                                                                                                         |
| mkdir assets/images                  | Creates a directory called "images" within assets                                                                                                          |
| touch hello.txt                      | Create a new file                                                                                                                                          |
| echo Hello                           | displays _Hello_                                                                                                                                           |
| echo "Hello World!" >> hello.txt     | Create a new file with the content "Hello world!"                                                                                                          |
| cat "hello.txt                       | Prints the content of hello.txt <br />cat only uses files as an input                                                                                      |
| cat hello.txt > world.txt            | Overwrites content of hello.txt into world.txt                                                                                                             |
| cat hello.txt >> world.txt           | Appends content of hello.txt into world.txt                                                                                                                |
| cp hello.txt hello.bak               | Copies hello.txt to a new file named hello.bak                                                                                                             |
| cp hello.txt /user/documents         | Copies hello.txt to a new directory <br /> (_It's also possible to copy more than one file. <br />Simply list all files and than add the target directy._) |
| cp \* /user/documents                | Uses wildcard to copy all files                                                                                                                            |
| cp \*.txt /user/documents            | Uses wildcard to copy all txt-files                                                                                                                        |
| cp h\* /user/documents               | Uses wildcard to copy all files starting with _h_                                                                                                          |
| mv                                   | Move a file or directory similar to _cp_ <br /> It can also be used to rename a file                                                                       |
| rm                                   | Removes a file similar to _cp_                                                                                                                             |
| rm -r                                | Removes a directory and all it's child directories                                                                                                         |
| \|                                   | Takes output of left command to the right command                                                                                                          |
| cat hello.txt \| wc                  | Counts lines, words and characters in hello.txt                                                                                                            |
| sort books.txt                       | Alphabetically sorts the content of books.txt <br /> without changing the file itlself                                                                     |
| uniq names.txt                       | Filters adjacent dublicate lines <br /> Not very effective on it's own because of the adjacent contidion                                                   |
| sort names.txt \| uniq               | Better way to filter duplicates                                                                                                                            |
| grep Harry names.txt                 | Searches for a string "Harry" in _names.txt_ <br />Note that grep is case sensitive.<br /> It can be made insensitive with the argument _-i_               |
| grep -Rl Potter /books/fantasy       | Searches the content of the directory for "Potter" <br /> _-R_ : searches recursive <br />_-l_ : lists only the file names and not the lines               |
| sed s/Ron/Harry/ harrypotter.txt     | Replaces the first instance of "Ron" in a line with "Harry". <br />It does not change the file itself.                                                     |
| sed -i s/Ron/Harry/g harrypotter.txt | Replaces the all instances of "Ron" in a line <br /> with "Harry" and saves the file.                                                                      |
| nana hello.txt                       | Opens the text application nano                                                                                                                            |
| history                              | Shows the previous entered commands                                                                                                                        |
| echo $HOME                           | Displays the variable _HOME_                                                                                                                               |
| env                                  | Returns the environment variables                                                                                                                          |
| export VARIABLENAME="variable value" | Define a global variable                                                                                                                                   |

## Aliases

Open _.bash_profile_ or .zshrc (if you use Zsh) with nano and create some shortcuts.

```bash
alias pd="pwd"
```

This will show you the current directory with the command _pd_ as well as with _pwd_.
