---
title: "Advanced practice with BASH"
teaching: 4 # teaching time in minutes
exercises: 6 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions

- Have you successfully completed the previous BASH practice exercises?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Practice more advanced BASH commands with loops
- Reinforce understanding of BASH scripting

::::::::::::::::::::::::::::::::::::::::::::::::

## Advanced BASH Scripting

Advanced userers of BASH often make use of loops to automate repetitive tasks. This can save time and reduce the risk of errors. Mastering loops is an essential skill for anyone looking to become proficient in BASH scripting. Also, experienced users often combine scripts with assigned variables to make their code more dynamic and adaptable to different situations.
Loops are no different than in other programming languades, and are used to repeat a specific block of code a certain number of times or until a particular condition is met. They are particularly useful when you need to perform the same operation on multiple files or datasets.
There are two main types of loops in BASH: `for` loops and `while` loops. We've set two examples below to illustrate how each loop works. Open the terminal from the Google Colab plarform first to try them out.

### For Loops
A `for` loop iterates over a list of items, executing a block of code for each item in the list. Here, we're going to add a header line to multiple CSV files that match a specific pattern (`*test.csv`) and generate a new file with this header.

```bash
# The command below iterates over all files that end with 'test.csv' in the current directory. Then, for each file, it uses the `sed` command to insert a new line at the top of the file with the text "This is a test". The output is redirected to a new file with the same name as the original file but with `.new.csv` appended to it.
for item in `ls *test.csv`; do
    sed '1i This is a test' $item > ${item}.new.csv
done
```

### While Loops
A `while` loop continues to execute a block of code as long as a specified condition is true. We've generated and example that could have an actual usage to general users. Here, we're going to create a new file named `myfile.txt` after a delay of 30 seconds. Then, during this 30 second gap, we will run a `while` loop to keep checking for the appearance of this file. Once the file is found (after the 30 second delay), the loop will print a message and exit.

```bash
# 1. Start a background process that creates the file after 30 seconds
(sleep 30 && touch myfile.txt) &

# 2. Set first a record of the initial state of the folder by creating a variable called "initial_count". Then, use a while loop to verify the existence of a new file, and write a message when it is found.
initial_count=$(ls -A | wc -l)
while [ "$(ls -A | wc -l)" -le "$initial_count" ]; do
    echo "Waiting for a new file..."
    sleep 5
done
echo "New file detected!"
```

## Bash Advanced Practice

Based on the examples above, scroll down to find a last series of exercises that will help you practice loops in BASH.
You'll need to use all the knowledge you've acquired so far (and probably online searching), to complete these last challenges. Nothing wrong in that by the way. Just remember that the goal is to get the correct output, not to match exactly the solution provided here.

## Exercises 4
Write a command line to execute what's asked in each challenge below. Right down your answer before opening the output cell to check our suggested commands. Use all available resources you need to complete the exercises.

::::::::::::::::::::::::::::::::::::: challenge 

## Challenge 4:

- Using a `for` loop, create a new file for each CSV file in the current directory that contains only the first 10 lines of each file. Name the new files with the original filename appended with `_top10.csv`.
- Using a `while` loop, count the numbers (separed by commas) in the mnist_test.csv file, from the fist row onwards, until it reaches 100000. Then print the total number of lines counted to reach that number. You may need to use a nested loop for this challenge. And here's another hint: you can use variables to keep track of the sum and the number of lines processed `;)`

:::::::::::::::::::::::: solution

## Output

```bash
$ for file in *.csv; do head -n 10 "$file" > "${file%.csv}_top10.csv"; done
# Our solution is a simple `for` loop that iterates over each CSV file in the current directory, using the `head` command to get the first 10 lines, and writing them to a new file with `_top10.csv` appended to the original filename.

$ sum=0; lines=0;
while IFS=, read -r -a nums; do
  ((lines++));
  for n in "${nums[@]}"; do
    ((sum+=n));
    if ((sum>=100000)); then
      echo "Reached sum $sum after $lines lines";
      break 2;
    fi;
  done;
done < mnist_test.csv
# Our suggested approach makes use of a `for` loop inside a `while` loop (nested loop), and also a `if` conditional statement. The `while` loop reads each line of the mnist_test.csv file, and the `for` loop iterates over each number in the line, adding it to the sum until the condition `if` (which checks when the sum reaches 100000) is met. All the above after setting two variables at the begining: `sum` to keep track of the total sum, and `lines` to count the number of lines processed.
# 
```

::::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: callout

- Congratulations! You've completed now a range of exercices from beginner to a more advanced level in BASH. You should now be comfortable using BASH commands to navigate the file system, edit files, and perform different data processing tasks. Keep practicing these commands to reinforce your skills and explore more advanced features of BASH as you progress in your scientific computing journey.

::::::::::::::::::::::::::::::::::::::::::::::::

[r-markdown]: https://rmarkdown.rstudio.com/
