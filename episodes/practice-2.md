---
title: "More hands-on practice with BASH"
teaching: 2 # teaching time in minutes
exercises: 10 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions

- Have you successfully completed the previous BASH exercises?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Test your knowledge on BASH commands in a terminal environment within Google Colab
- Reinforce understanding of BASH command structure

::::::::::::::::::::::::::::::::::::::::::::::::

## Hands-on Practice with BASH (part 2)

Based on your previous exercises, use the same terminal from the Google Colab platform to test your knowledge on BASH commands. Start by typing `cd sample_data` to access the folder that contains the files you'll be using during this training. Scroll down to find a series of exercises which will demand choosing for specific flags to generate the desired output.
But first, you'll need the same table.tsv generated in the previous exercises to complete these challenges. If you don't have it anymore, you can recreate it by following the steps in the previous episode.

## Exercises 3
Write a command line to execute what's asked in each challenge below. Right down your answer before opening the output cell to check which of your command were correct. Please remember that you can use `name-of-program --help` to obtain more information about each command and their optional flags. Also, keep in mind that multiple commands can be combined using the pipe `|` symbol. One last thing to know is that is not unusual to use different commands to get same the desired output. So don't worry if your answer is different from the solution provided. Getting the correct output is what matters the most.

::::::::::::::::::::::::::::::::::::: challenge 

## Challenge 3:

- Print only the 7th, 8th and 9th columns of the file `table.tsv`.
- Print only the number of lines of the file `table.tsv`.
- Select only lines which do not show Putative in the annotation column of the file `table.tsv`, collect the third column and append the output to the previously created `annotations.txt` file.
- Print the first 5 lines of the file `table.tsv` in reverse order.
- Using `awk`, print `table.tsv` content with columns 3, 2 and 1 in this order and as a tab separated value.
- Print the first 3 lines of the file `table.tsv` starting from line 7 (i.e., lines 7, 8 and 9) usind `sed`.

:::::::::::::::::::::::: solution

## Output

```bash
$ head -n 9 table.tsv | tail -n 3
$ wc -l table.tsv
$ grep -v "Putative" table.tsv | cut -f 3 >> annotations.txt
$ head -n 5 table.tsv | tac
$ awk -v OFS='\t' '{print $3, $2, $1}' table.tsv
$ sed -n '7,9p' table.tsv

```

::::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: callout

- Once you've completed the exercices above, feel free to explore more advanced BASH commands at the next lesson.

::::::::::::::::::::::::::::::::::::::::::::::::

[r-markdown]: https://rmarkdown.rstudio.com/
