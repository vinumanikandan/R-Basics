# R-Basics

R is a statistical programming language and is a powerful tool for data processing and manipulation. This module will be introduction to R and RStudio. You will learn about the different R visualization packages and how to create visual charts using the plot function.

## What is R ?

- R is a free open source software environment for statistical computing and graphics.
  
- It compiles and runs on a wide variety of UNIX platforms, Windows and MacOS.

- Command-line driven programming (no drop-down menus or buttons)


- R is an integrated suite of software facilities for data manipulation, calculation , graphical display and machine learning algorithm. It includes 
  - an effective data handling and storage facility,
  - a suite of operators for calculations on arrays, in particular matrices,
  - a large, coherent, integrated collection of intermediate tools for data analysis,
  - graphical facilities for data analysis and display either on-screen or on hardcopy with publication-quality plots, and
  - a well-developed, simple and effective programming language which includes conditionals, loops, user-defined recursive functions and input and output facilities.

[More information about R](https://www.r-project.org/)

[Download & install R](https://cloud.r-project.org)

## What is R Studio ?

- RStudio is an integrated development environment (IDE) for R. 

- It includes a console, syntax-highlighting editor that supports direct code execution, as well as tools for plotting, history, debugging and workspace management

- RStudio is available in open source and commercial editions and runs on the desktop (Windows, Mac, and Linux)

![Rstudio Screenshot](images/Rstudio.png)


## Different Panels in R Studio

![Rstudio Panels Screenshot](images/Rstudio_Panel.png)

[More information about R Studio](https://posit.co)

[Download & install R Studio](https://posit.co/downloads/)


## Scripts and workspace

**R script (.R file)**

- Very useful instead of typing commands on the console.
- allows you to keep track of what you are doing and make any modification easier
- To actually execute some commands, you can select the lines and run the execution
  
 **Workspace (.Rdata file)** 
- The internal memory where R will store the objects you created during the session.
- To save only specific R objects: save(object_name(s),"name_of_file.RData")
- To save your entire workspace: save.image("name_of_file.RData")
- To load your workspace / specific R objects: load("name_of_file.RData")

## R Markdown

 R Markdown provides framework where single R Markdown file can generate
  - execute a Rscript
  - generate high quality reports that can be shared with an audience
  - fully reproducibel documentation with wide variety of dynamic output formats

![Rmd output Screenshot](images/Rmd.png)

[More about R Markdown ](https://rmarkdown.rstudio.com/lesson-2.html)


## Basic information on Syntax

- anything after a hash (#) is ignored – e.g. comments
- the variables are **case sensitive**:  variable name Data is not as same as data/DATA
- variable names can be alphanumeric include A-Z, a-z, 0-9, but can not start with a number
- variable names cannot have spaces in between. Spaces should be filled with "_" or "-" ie. my_data
- Always keep an informative vraiable name like "class_data" not "cd"
- Commands can be separated by ; or newline

## Basic Data Types in R

- **numeric** -  data are numbers that contain a decimal. Actually they can also be whole numbers  (10.5, 55, 787)

- **integer** -  whole numbers (those numbers without a decimal point).(1L, 55L, 100L, where the letter "L" declares this as an integer)

- **complex**  - (9 + 3i, where "i" is the imaginary part)

- **character** - data are used to represent string values  (a.k.a. string) - ("k", "R is exciting", "FALSE", "11.5")

- **logical**  (a.k.a. boolean) - (TRUE or FALSE)



## Operators

**Arithmetic Operators**

|Operator|Name|Example|
|:---:|:---:|:---:|
|+|Addition|x + y|
|-|Subtraction|x - y|
|*|Multiplication|x * y|
|/|Division|x / y|
|^|Exponent|x ^ y|
|%%|Modulus (Remainder from division)|x %% y|
|%/%|Integer Division|x%/%y|


**Comparison Operators**

|Operator|Name|Example|
|:---:|:---:|:---:|
|==|Equal|x == y|
|!=|Not equal|x != y|
|>|Greater than|x > y|
|<|Less than|x < y|
|>=|Greater than or equal to|x >= y|
|<=|Less than or equal to|x <= y|

**Logical Operators**


|Operator|Description|
|:---:|:---:|
|&|Element-wise Logical AND operator. It returns TRUE if both elements are TRUE|
|&&|Logical AND operator - Returns TRUE if both statements are TRUE|
|\||Elementwise- Logical OR operator. It returns TRUE if one of the statement is TRUE|
|\|\||Logical OR operator. It returns TRUE if one of the statement is TRUE.|
|!|Logical NOT - returns FALSE if statement is TRUE|


## First Run in R 

We’ll use the ‘Console’ panel first and do basic arithmetics

``
1+2
``
**[1] 3**


```
2^5+7
```
**[1] 39**


```
2^(5+7)
```
**[1] 4096**

```
log(20+pi)
```
**[1] 3.141632**


## Task 1: Find log2 of sum of three numbers 56,40 and 22

<details>

<summary>Task 1 answer </summary>

```

log2(22+40+56)

```
</details>

## More information or help

More information of a function can be accessed from R by using either one of the syntax. 

```
?log

```
 **or** 
 
```
help(log)
```

![Rstudio Screenshot](images/help.png)



## Converting normal commands a  programming language

By assigning the data to to meaning full variaable we can reuse the variable multiple times 

```
Num_1<-1
Num_2<-2
Sum_12<-Num_1+Num_2 
Sum_12
```
**[1] 3**

## Task 2: 
1  Create 3 variable 'a1,a2,a3' for 3 numbers  56,40 and 22 
2. Create a sum of these 3 variables and store them in new variable A123 and 
3. Log2 transform A123 and store in a new variable Log_A123. Display A123 and LA123

<details>

<summary>Task 2 answer </summary>

```
a1<-56
a2<-40
a3<-22

A123<-a1+a2+a3
A123

Log_A123<-log2(A123)
Log_A123
```
</details>


## Creating Vectors & some basic operations

List of items that are of the same types are called vectors 

In the example below, we create a vector variable called fruits, that combine strings:

**Vector of strings**
```
fruits <- c("banana", "apple", "orange")

# Print fruits
fruits

```

**Vector of numerical values**
```
numbers <-c(1.3, 0.32,10.5, 5.9, 6.3)

# Print numbers
numbers

```

**[1] 1.30 0.32 10.5 5.90 6.30**

## Operations in vector
Operations in vectors work element by element in an sequenctial format

```
multi_by<-5
numbers*multi_by

```
**[1]  6.5  1.6 52.5 29.5 31.5**

if a vector is short, R recycles it (reuses it) as needed

```
multi_by<-c(5,1)
numbers*multi_by
```

**[1]  6.50  0.32 52.50  5.90 31.50**

In the above example the vectors are multipled by sequential order and resued till the length of the largest vector

**(1.3*5) (0.32*1) (10.5*5)  (5.90*1) (6.30*5)**


## Generating sequencial numbers

Instead of hard coding the sequencial numbers such as 'c(1,2,3,4,5,6,7,8,9,10)'

```
1:10

```
will do the same output **[1]  1  2  3  4  5  6  7  8  9 10**

In order to create rever sequential number

```
10:1

```
**[1] 10  9  8  7  6  5  4  3  2  1**

## Using seq()

Another method to generate sequential number is to use **seq() function**  which is more flexible

```
seq(from=1, to=10)

```

## Task 3: 
Find what are the available parameters/options associated with function seq()
<details>
  <summary>Task 3 answer</summary>
  
```
help(seq)
```
![sequence generation  help Screenshot](images/seq.png)

</details>

## Task 4: 

- 1 create a vector of even numbers between 1 and 10

- 2 create a vector of odd numbers between 1 and 10 

<details>
  <summary>Task 3 answer</summary>
  
```
even_num<-seq(from=2, to=10,by=2)
even_num

odd_num<-seq(from=1, to=10,by=2)
odd_num

```

</details>

