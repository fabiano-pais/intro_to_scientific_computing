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

Start by typing `cd sample_data` to access a folder that already contains some files you'll be using during our training. Then, scroll down here to find a series of exercises that will help you practice the most important BASH commands. Observe the commands you'll be using, along with its syntax at each example.

The first thing you must know is that, in general, there are two key elements required to execute a BASH command:

 1. The program, which will execute an specific task;
 2. The file or input data the program will work on;

Optional flags that modify the behavior of the program. The available flags for each program can be accessed by typing `name-of-program --help`. Try it with the commands you'll learn below.

## Commands

Learn the commands below as they're the most used ones in BASH:

- `ls` – listing the content of a folder
- `cd` – to access different folders
- `pwd` – shows your current folder
- `cp` – copy file(s) or folder(s)
- `mv` – move file(s) or folder(s)
- `rm` – remove/erase file(s) or folder(s)
- `mkdir` – create new folder
- `touch` – create new file
- `wc` – word count will give total characters, words and lines
- `head` – print the first 10 lines of a file
- `tail` – print the last 10 lines of a file
- `more` – show the content of a file progressively (good for big files)
- `sort` – organize your data by specific order
- `cut` – print selected columns from a file
- `grep` – used to search for patterns in a file
- `paste` – merges the content of one file with a second file side-by-sing horizontally
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
Open your terminal and execute the commands below to practice BASH commands. Write down the output of each coommand as we will check it at the end of this exercise.
```bash
$ mkdir course_folder
$ cd course_folder
$ pwd
$ touch course_file.txt
$ mkdir folder
$ mv course_file.txt folder/
$ cd folder/
$ cp course_file.txt ../
$ cd ..
$ rm course_file.txt
$ rm -r folder/
```
::::::::::::::::::::::::::::::::::::: challenge

## Challenge 1: Order the sequence of events from the commands above

- Go to ther new folder.
- Enter a folder you’ve created.
- Create a new directory to work.
- Move your empty file to the folder you`ve just created.
- Show your current path.
- Erase the folder you've created
- Erase course_file.txt at your current folder.
- Create a new folder.
- Copy course_file.txt to the previous folder on your current path.
- Create a file.
- Go to the previous folder on your current path.

:::::::::::::::::::::::: solution

## Output

1. Create a new directory to work.
2. Enter a folder you’ve created.
3. Show your current path.
4. Create a file.
5. Create a new folder.
6. Move your empty file to the folder you`ve just created.
7. Go to ther new folder.
8. Copy course_file.txt to the previous folder on your current path.
9. Go to the previous folder on your current path.
10. Erase course_file.txt at your current folder.
11. Erase the folder you've created.

::::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: callout

- You can combine commands using the pipe operator (|) to create more complex workflows.
- You can redirect the standard output from one command to new files using the greater-than symbol (>). Example: `head -n 5 table.tsv > top5.tsv` will create a new file named top5.tsv containing the first 5 lines of table.tsv.
- Type “history” to see (at the standout) the commands you’ve entered previously.

::::::::::::::::::::::::::::::::::::::::::::::::

### Exercise 2

In order to run the next exercise, make sure you're in the `sample_data` folder where you started before. If not, type `cd ~/sample_data` to get back to it.
Create a new file named table.tsv and paste the content below into it.
In order to create and edit the file, you can use `vim table.tsv` command. Copy the data below (don't forget the header) and past the content at the terminal, press `ESC`, then `:`, then `wq` and `ENTER` to save and exit vim editor.

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
And here are the commands to practice with this new file. Remember to write down the output of each command as we will check it at the end of this exercise.
```bash
$ wc table.tsv
$ head table.tsv
$ tail table.tsv
$ more table.tsv
$ sort -k3 table.tsv
$ cut -f 2 table.tsv
$ cut -f 3 table.tsv > annotations.txt
$ grep 'Putative' lipids.txt | head -n 5
$ sed 's/Putative/Unknown/g' table.tsv
$ paste table.tsv annotations.txt > merged.tsv
````
::::::::::::::::::::::::::::::::::::: challenge 

## Challenge 2: Order the sequence of events from the commands above

- Print only the second column from the file.
- Print the last 10 lines.
- Print the first 10 lines.
- Copy the content of the third column to a new file named annotations.txt.
- Get the counts of characters, words and lines from your file.
- Search the occurrence of a specific pattern "putative" at the file.
- Merge the content of both files, table.tsv and annotations.txt, into a new file named merged.tsv.
- Replace the word "Putative" with "Unknown" throughout the file and print the first 5 lines only.
- Show the content of the whole file progressively; `cat` may also be used to show the content of a file but it does not allow progressive visualization.
- Print the file in an alfabetically ordered fashion by the element at the third column on each line

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
