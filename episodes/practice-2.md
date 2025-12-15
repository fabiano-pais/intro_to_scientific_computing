---
title: "Hands-on Practice with BASH"
teaching: 2 # teaching time in minutes
exercises: 10 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions

- Have you downloaded our `{jupyter notebook course file}`?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Practice basic BASH commands in a jupyter notebook environment
- Demonstrate understanding of BASH command structure

::::::::::::::::::::::::::::::::::::::::::::::::

## Hands-on Practice with BASH

Once you've downloaded the jupyter notebook file, please open the file with a program of your choice such as [VScode](https://code.visualstudio.com), [Google Colab](https://colab.research.google.com) or [JupyterLab](https://jupyter.org) for example.

Then, scroll down to find a series of exercises that will help you practice the most important BASH commands. Each exercise contains a brief description of the command you'll be using, along with its syntax and an example.

The first thing you need to know is that there are two key elements required to execute a BASH command:

 1. `program` will execute an specific task.
 2. `options` can change the output of a program by modifying the execution of the program.

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor

Inline instructor notes can help inform instructors of timing challenges
associated with the lessons. They appear in the "Instructor View"

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

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
- `paste` – merges the content of one file with a second file starting from the right end of each row at the second file
- `cat` – merges the content of one file with a second one starting from the end of the second file

## Exercises

### Exercise 1
Open your terminal (in jupyter notebook) and follow the commands below to practice BASH commands:
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
$ rm folder/course_file.txt
```
::::::::::::::::::::::::::::::::::::: challenge 

## Challenge 1: Order the sequence of events from the commands above

- Go to ther new folder.
- Enter a folder you’ve created.
- Create a new directory to work.
- Move your empty file to the folder you`ve just created.
- Show your current path.
- Erase course_file.txt at folder (which in not the file at your current folder).
- Create a new folder.
- Copy course_file.txt to the previous folder on your current path.
- Create a file.
- Go to the previous folder on your current path.

:::::::::::::::::::::::: solution

## Output

1. Create a new directory to work
2. Enter a folder you’ve created
3. Show your current path
4. Create a file
5. Create a new folder
6. Move your empty file to the folder you`ve just created
7. Go to ther new folder
8. Copy course_file.txt to the previous folder on your current path
9. Go to the previous folder on your current path
10. Erase course_file.txt at folder (which in not the file at your current folder)

::::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: callout

- Use up/down arrows on your keyboard to check previous commands
- Type “history” to see (at the standout) the commands you’ve entered previously
- Try using the help menu from programs you’ve just used (usually accessed by typing –help)

::::::::::::::::::::::::::::::::::::::::::::::::

### Exercise 2

In order to run the next exercise, we'll use the same folder from the previous exercise and, so please make sure you're at the correct path at your terminal.
Create a new file named table.tsv and paste the content below into it:

```plaintext
GeneID	Expression	Annotation
Gene001	23.5	Putative kinase
Gene002	45.2	Putative phosphatase
Gene003	12.8	Transcription factor
Gene004	67.1	Membrane protein
Gene005	34.6	Putative transporter
Gene006	78.9	Structural protein
Gene007	56.3	Enzyme
Gene008	89.0	Signal transducer
Gene009	15.4	Receptor
Gene010	42.7	Putative regulator
Gene011	29.3	Chaperone
Gene012	53.8	Metabolic enzyme
```
Here are the commands to practice with this new file:
```bash
$ wc table.tsv
$ head table.tsv
$ tail table.tsv
$ more table.tsv
$ sort table.tsv
$ cut -f 2 table.tsv | sort -n
$ cut -f 3 table.tsv > annotations.txt
$ grep 'Putative' lipids.txt
$ sed 's/Putative/Unknown/g' table.tsv
$ paste table.tsv annotations.txt > merged.tsv
````
::::::::::::::::::::::::::::::::::::: challenge 

## Challenge 2: Order the sequence of events from the commands above

- Print only the second column from the file in a numeric order.
- Print the last 10 lines.
- Print the first 10 lines.
- Copy the content of the third column to a new file named annotations.txt.
- Get the counts of characters, words and lines from your file.
- Search the occurrence of a specific pattern "putative" at the file.
- Merge the content of both files, table.tsv and annotations.txt, into a new file named merged.tsv.
- Replace the word "Putative" with "Unknown" throughout the file.
- Show the content of the whole file progressively.
- Print the file in an ordered fashion by element at the first column on each line

:::::::::::::::::::::::: solution

## Output

1. Get the counts of characters, words and lines from your file.
2. Print the first 10 lines.
3. Print the last 10 lines.
4. Show the content of the whole file progressively.
5. Print the file in an ordered fashion by element at the first column on each line
6. Print only the second column from the file in a numeric order.
7. Copy the content of the third column to a new file named annotations.txt.
8. Search the occurrence of a specific pattern "putative" at the file.
9. Replace the word "Putative" with "Unknown" throughout the file.
10. Merge the content of both files, table.tsv and annotations.txt, into a new file named merged.tsv.

::::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: callout

- Access the help menu from programs you’ve just used, usually accessed by typing 'name-of-the-program -–help', to explore more options for each command.
- Try combining commands using the pipe operator (|) to create more complex workflows.
- Try redirecting output to new files using the greater-than symbol (>).

::::::::::::::::::::::::::::::::::::::::::::::::

[r-markdown]: https://rmarkdown.rstudio.com/
