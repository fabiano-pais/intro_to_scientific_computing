---
title: "Hands-on Practice with BASH"
teaching: 2 # teaching time in minutes
exercises: 10 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions

- Have you set up your Google account yet?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Practice basic BASH commands in a terminal environment within Google Colab
- Demonstrate understanding of BASH command structure

::::::::::::::::::::::::::::::::::::::::::::::::

## Hands-on Practice with BASH

Open your Colab account (https://colab.research.google.com). Colab is not a separate service, but rather a part of your Google account. Once opened, click at the "Terminal" icon at the lower left sidebar to open a terminal window within Colab. This terminal will act as your BASH environment where you'll be able to practice the commands you'll learn here.

Scroll down to find a series of exercises that will help you practice the most important BASH commands. Check the "Commands" section below to see a brief description of the commands you'll be using.

The first thing you must know is that, the basic syntax for executing a command requires at least two elements:

 1. The command, which will execute an specific task;
 2. The file or input data the command will work on.;

Optional flags, that modify the behavior of the command, can also be used. The available flags for each command can be accessed by typing `command --help` (for example: `ls --help`).

## Commands

Learn the commands below as they're the most used ones in BASH:

- `ls` – listing the content of a folder
- `cd` – used to access different folders
- `pwd` – shows your current folder (or PATH) in the file system
- `cp` – copy file(s) or folder(s) to a new location
- `mv` – move file(s) or folder(s) to a new location
- `rm` – remove/erase file(s) or folder(s)
- `mkdir` – create new folder
- `touch` – create new file
- `wc` – shows the total number of characters, words and lines of a file
- `head` – print the first 10 (default) lines of a file
- `tail` – print the last 10 (default) lines of a file
- `more` – show the content of a file progressively (good for big files)
- `sort` – organize your data by specific order of a given column 
- `cut` – print selected columns from a file
- `grep` – used to search for patterns in a file
- `paste` – merges the content of one file with a second file side-by-sing (horizontally)
- `cat` – show the content of a file
- `sed` – stream editor for filtering and transforming text
- `awk` – a programming language for pattern scanning and processing

::::::::::::::::::::::::::::::::::::: callout

- Also consider accessing (https://linuxcommand.org/lc3_man_page_index.php) for more information about BASH commands.
- Use up/down arrows on your keyboard to check previously executed commands.
- When typing long commands, use the tab key to autocomplete program names and file/folder names.

::::::::::::::::::::::::::::::::::::::::::::::::

## Exercises

### Exercise 1
Use your terminal to run the commands below to practice BASH. Write down the output of each coommand as we will check it at the end of this exercise. 
Before and after executing each command, type `ls` and press `ENTER` to see the content of your current folder (and how this content changes after each command).

```bash
# Please, note that the `$` symbol represents the terminal prompt and should not be typed.
$ mkdir course_folder
$ cd course_folder
$ pwd
$ touch course_file.txt
$ mkdir course_folder2
$ mv course_file.txt course_folder2/
$ cd course_folder2/
$ cp course_file.txt ../
$ cd ..
$ rm course_file.txt
$ rm -r course_folder2/
```
::::::::::::::::::::::::::::::::::::: challenge

## Challenge 1: Order the sequence of events from the commands above

- Click the output box below to reveal the correct order of events from the commands above.

:::::::::::::::::::::::: solution

## Output

1. Create a new directory to work called `course_folder`.
2. Enter a folder you’ve created.
3. Show your current directory (or path).
4. Creates a file.
5. Creates a new course_folder2.
6. Move your empty file to the second folder you`ve created.
7. Go to ther new folder.
8. Copy course_file.txt to the previous folder from your current directory (or path).
9. Go to the previous folder from your current path.
10. Erase course_file.txt at your current folder.
11. Erase the second folder you've created.

::::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: callout

- You can combine commands using the pipe operator (|) to create more complex workflows.
- You can redirect the standard output from one command to new files using the greater-than symbol (>). Example: `head -n 5 table.tsv > top5.tsv` will create a new file named top5.tsv containing the first 5 lines of table.tsv.
- Type “history” to see (at the standout) the commands you’ve entered previously.

::::::::::::::::::::::::::::::::::::::::::::::::

### Exercise 2
This exercise requires creating first a new file named table.tsv. The content of the file was placed below. Please select and copy all the content below (including the header) to create the file.
```plaintext
GeneID	Expression	Annotation
Gene001	23.5	Putative Kinase Gene
Gene002	45.2	Putative Phosphatase Gene
Gene003	12.8	Transcription Factor
Gene004	67.1	Membrane Protein
Gene005	34.6	Putative Transporter Gene
Gene006	78.9	Structural Protein
Gene007	56.3	Enzyme
Gene008	89.0	Signal Transducer
Gene009	15.4	Receptor
Gene010	42.7	Putative Regulator Gene
Gene011	29.3	Chaperone
Gene012	53.8	Metabolic Enzyme
```
To create the file, run the next command to create it:
```bash
$ vim table.tsv
```
As you can see, your terminal now looks different. `Vim` is a text editor, so please paste the content you've copied from above at your terminal. USE THE ARROWS IF YOU NEED TO MAKE ANY CORRECTION TO THE TEXT AT ANY GIVEN ROW (the mouse will not work). Then press `ESC`, then `:`, then `wq` and finally `ENTER` to save and exit vim editor.
Once the above is complete, please run the commands below to practice with the new table. Remember to write down the output of each command as we will check it at the end of this exercise.
```bash
$ wc table.tsv
$ head table.tsv
$ tail table.tsv
$ more table.tsv
$ sort -k3 table.tsv
$ cut -f 2 table.tsv
$ cut -f 3 table.tsv > annotations.txt
$ grep 'Putative' table.tsv | head -n 5
$ sed 's/Putative/Unknown/g' table.tsv
$ paste table.tsv annotations.txt > merged.tsv
````
::::::::::::::::::::::::::::::::::::: challenge 

## Challenge 2: Order the sequence of events from the commands above

- Click the output box below to reveal the correct order of events from the commands above.

:::::::::::::::::::::::: solution

## Output

1. Get the counts of characters, words and lines from your file.
2. Print the first 10 lines.
3. Print the last 10 lines.
4. Show the content of the whole file progressively.
5. Print the file in an alfabetically ordered fashion by the element at the third column on each line
6. Print only the second column from the file.
7. Copy the content of the third column to a new file named annotations.txt.
8. Search the occurrence of a specific pattern "putative" at the file.
9. Replace the word "Putative" with "Unknown" throughout the file and print the first 5 lines only.
10. Merge the content of both files, table.tsv and annotations.txt, into a new file named merged.tsv.

::::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

[r-markdown]: https://rmarkdown.rstudio.com/
