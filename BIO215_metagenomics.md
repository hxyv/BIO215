# UNIX and Linux

## Introduction

Here we'll explore the UNIX operating system, with a focus on user-friendly Linux, specifically Debian-based distributions like Ubuntu. Whether you're a seasoned Unix/Linux user or a newbie, understanding UNIX is crucial. Why? Because nearly all major operating systems, like MacOS and Windows, rely on Unix at their core. It's the foundation for serious computational work, including genomics research. So, let's dive into the world of bioinformatics, where UNIX is your key to scientific discovery.

## Some terminology

Here are some terms that you should know before we start (Table from [_Happy Belly Bioinformatics_](https://astrobiomike.github.io/unix/))

| Term                    | Explanation                                                                                                                                                                                                                               |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `shell`                 | What we use to talk to the computer; anything where we are pointing and clicking with a mouse is a **G**raphical **U**ser **I**nterface (**GUI**) shell; something with text only is a **C**ommand **L**ine **I**nterface (**CLI**) shell |
| `command line/terminal` | A text-based environment capable of taking input and providing output                                                                                                                                                                     |
| `Unix`                  | A family of operating systems (we also use the term “Unix-like” because one of the most popular operating systems derived from Unix is specifically named as [_not_ being Unix](https://en.wikipedia.org/wiki/GNU))                       |
| `bash`                  | The most common programming language used at a Unix command-line                                                                                                                                                                          |

## UNIX directory structure

The key UNIX directories are (Table from [TheMulQuaBio](https://mhasoba.github.io/TheMulQuaBio/notebooks/01-Unix.html)):

| Directory | Description                                                                               |
| --------- | ----------------------------------------------------------------------------------------- |
| `/`       | Is the “root” directory                                                                   |
| `/data`   | Contains data                                                                             |
| `/dev`    | Contains files connecting to devices (keyboard, mouse, screen, etc.)                      |
| `/home`   | Your home directory; this is where all your documents are and where you will usually work |
| `/tmp`    | Contains temporary files                                                                  |
| `/bin`    | Contains basic programs                                                                   |
| `/etc`    | Contains configuration files                                                              | 

This hierarchical directory structure makes navigating your computer from the terminal/shell or encoding this navigation in your computer programs easier.

![[tree 1.png#pic_center|500]]

- **UNIX directory structure.**  The UNIX directory (same as “Folder”) structure is hierarchical, with a single tree starting from the “root” (`/`). This is quite unlike Windows or MS-DOS, where there are separate trees for disk partitions, removable media, network, etc. 

>[!question]- How to represent the "data" folder under the user "user1"?
>`/home/user1/data/`

> [!Tips]  Tilde `~`
> The path `/home/yourname/` can be replaced with shorthand `~` (important to remember!). So, for example, the command `cd /home/yourname/Documents` is the same as the command `cd ~/Documents` 

During this lab practical session, we will be working with metagenomic data on the **Linux** platform. Linux is an open-source operating system that [Linus Torvalds](https://en.wikipedia.org/wiki/Linus_Torvalds) originally developed in 1991. It's distinguished by its "**Unix-like**" architecture. The term "Linux" is derived from the kernel it utilizes. This robust operating system falls into a distinct category of computer software, enabling applications and users to seamlessly interact with computer hardware to perform specific tasks.

# Linux practical session

## Log in to RStudio server

RStudio Server is a web-based integrated development environment (IDE) for the R programming language. It allows users to access and work with R from a web browser, making it a versatile tool for data analysis and statistical computing.

To access RStudio Server, open your web browser and enter the IP address ([10.7.6.100:8787](http://10.7.6.100:8787/) in this case) in the address bar, then press `ENTER`. You will be directed to the login window. Enter your username and password to log in.

![[Screenshot 2023-10-29 at 10.54.03.png#pic_center|500]]

>[!warning] Connection restriction
>Access to the server is restricted to XJTLU campus's Wi-Fi network. If you are off-campus, you will need to connect to the [XJTLU VPN ](https://guide.xjtlu.edu.cn/pdf/mits/XJTLU%20VPN%20%20User%20Guide.pdf) to access the server.

## Terminal in RStudio server

In RStudio Server, you can access the terminal or command-line interface directly within the RStudio environment. This allows you to run command-line utilities and perform system-related tasks right from your web-based RStudio interface. 

- In RStudio Server, you can access the terminal by clicking on the "Terminal" tab located in the left-bottom of the RStudio interface. It's represented by a command prompt icon.

![](terminal.png#pic_center)

- Once the terminal is open, you can use it just like any other Linux terminal. You can run command-line utilities, execute shell scripts, navigate the file system, and perform various system-related tasks.

- You can type commands directly into the terminal, and the output will be displayed within the terminal pane.

- Let’s look at key features of the bash shell/terminal:

  - The shell, by default, automatically starts in your home directory `/home/yourname/`

  - The start of the command prompt, where you will type your commands is indicated by a `:~$`)

  - The text before the `:~$` tells you what the name of the current user is (the part before the `@`), and the name of the computer (the part after the `@` upto the `:~$`).

![[terminal2.png#pic_center|]]

## Linux basic command first glance

| Command | Explanation                                                           |
| ------- | --------------------------------------------------------------------- |
| `passwd`  | Set your password                                                     |
| `pwd`     | Show current working directory                                        |
| `mkdir`   | Create a directory                                                    |
| `ls`      | List all the files/folders                                            |
| `cd`      | Change the current working directory to another folder                |
| `~`       | Your home directory                                                   |
| `echo`    | Display text or messages to the terminal or console                   |
| `cat`     | View text files, concatenating files, etc.                            |
| `head`    | Display the beginning (or "head") of a text file.                     |
| `tail`    | Display the end (or "tail") of a text file                            |
| `grep`    | Searching and filtering text based on patterns or regular expressions |
| `cp`      | copy files and directories from one location to another               |
| `rm`      | Remove or delete files and directories                                |
| `mv`      | Move or rename files and directories                                  |
| `htop`    | An interactive system monitoring tool for Linux                       |


## pwd

Print Working Directory. It prints the path of the working directory, starting from the root.

```bash
pwd
#/home/tangmin02
```

### Getting help

Getting help information of one command by adding the parameter `--help` directly behind the command.

```bash
pwd --help
```


## mkdir

Make directory. It allows the user to create directories.

```bash
mkdir test1 # This command could generate a folder (`test1` in this case)
```

Tree view of current directory structure:

![[tree2.png#pic_center|500]]

## ls

List directory contents. This command gives information about each file-like objects pointed by the paths given on the command line.

```bash
ls
# R  test1
```

### ll

`ll` is not a standard Unix command; however, it is commonly established as an alias or shorthand for `ls -l`. This means you can conveniently use `ll` directly in the command line to access the detailed, long-format listing of files and directories.

```bash
ll
```

![[Screenshot 2023-10-28 at 16.32.36.png#pic_center|500]]

- `ll` offers a more detailed view, including file attributes and additional information.
- `ll` command lists all the files in my home directory including the hidden files that names start with `.` (e.g. ".bash_history").
- [Understanding the results returned by `ll`](https://superuser.com/questions/171858/how-do-i-interpret-the-results-of-the-ls-l-command):
![[Screenshot 2023-10-28 at 16.37.47.png#pic_center|700]]

## cd

Change directory. It is used to change current working directory.

```bash
pwd # Printing where are you now
cd test1 # Then, using this command to change the directory to test1 folder
pwd # Now you are in test1 folder
cd .. # `..` denotes the upper directory
cd # If you type `cd` without any parameter (or use `cd ~`), you will directly go to your home directory
```

## echo

`echo` is commonly used in shell scripts to display a message or output the results of other commands.

```bash
echo Hello, world!
#Hello, world!
```

You can use `echo` to write something (or nothing) into a new file.

```bash
echo -e "What is the best way to learn Linux? \n\tYou need to practice it as much as you can!" > ~/test1/answer.txt
# -e is to displays an escape character. 
#`>` means to write the string to answer.txt file in ~/test1/ this directory.
```

## cat

This command could show you the content of a file.

```bash
cat ~/test1/answer.txt # Let's check the file content generated in the previous step.
#What is the best way to learn Linux?
#    You need to practice it as much as you can!
```

You can also use `cat` to concatenate files.

```bash
# Let's create two files first
echo "This is file 1." > ~/test1/file1.txt
echo "This is file 2." > ~/test1/file2.txt

# Now, use `cat` to concatenate!
cd ~/test1/
cat file1.txt file2.txt > ~/test1/file.concatenated.txt

# Let's check the result.
cat ~/test1/file.concatenated.txt
#This is file 1.
#This is file 2.
```

## Absolute path or Relative path

In Linux, the absolute path will always start with "/", representing the root directory.

```bash
/home/tangmin02/test1/answer.txt
```

Tree view of current directory structure:

![[tree3.png#pic_center|500]]

While the relative path refers to the present directory. For example, if I am in my home directory (i.e. "/home/tangmin02/") and want to to access the "answer.txt" file (full path: "/home/tangmin02/test1/answer.txt"), I will use the relative path to give the direction of the file from the present directory.

```bash
cd /home/tangmin02/
cat test1/answer.txt
```

### Using relative path with `.` and `..` directories

In relative path, you can also navigate from the current or parent directory using the single `.` or `..` dot.

For example, if I am in my home directory "tangming02".
- `.` refers to the current directory in the path (i.e. `./` means "/home/tangmin02/" in this case)
- `..` refers to the parent directory in the path (i.e. `..` means "/home/" in this case)
If I want to navigate to the "test1/" directory, either I can specify the directory name "test1/" or use "./test1/" to specify the directory name.

```bash
cd test1/
# OR
cd ./test1/
```

And if I want to navigate to home directory (i.e. "/home/"), I can either specify the absolute path or use the double dot to refer to the parent directory.

```bash
cd /home/
# OR
cd ..
```

## head & tail

The `head` command can be used to view the contents of the beginning of the file. On the contary, `tail` command can be used to view the contents at the end of the file.

```bash
head --help > ~/test1/help.txt # Let's generate a help.txt which contain the explanation of head command
head ~/test1/help.txt # Then, checking the content of this file.
head -n 20 ~/test1/help.txt # Paremeter -n NUMBER can specify the number of reading rows, `10` means the first 10 lines of help.txt.

tail ~/test1/help.txt # Checking the tail information of help.txt.
```

## grep

Global regular expression. This command is used to find the qualified string or regular expression in the file.

```bash
grep "help" ~/test1/help.txt # Find the line containing the "help" in the file ~/test1/help.txt.
```

## cp

Copy file. The command is mainly used to copy files or folder.

```bash
cd ~/test1/
mkdir data # Let's create a "data" folder inside the test1 folder to store our data.
ls # Check the folders and files in test1
cp ~/test1/help.txt ~/test1/data/ # Copy the file ~/test1/help.txt to ~/test1/data/
ls ~/test1/data/ # Now, we have help.txt file in data folder.
```

## rm

Remove. The command is used to delete a file or folder.

```bash
rm ~/test1/help.txt # Let's remove the file (~/test1/help.txt) we copied in the previous step.
ls ~/test1/ # Now, the file is removed.
```

## mv

Move file. This command is used to rename a file or folder, or move a file or folder to another location.

```bash
ls ~/test1/ # Let's see what files are in the test1
mv ~/test1/answer.txt ~/test1/data/ # We move the file (~/test1/answer.txt to ~/test1/data/ folder).
ls ~/test1/
ls ~/test1/data/ # Let's check where is the answer.txt file now.

ls ~/test1/data/ # We have one file in data folder
mv ~/test1/data/help.txt ~/test1/data/helpOfHead.txt # We use the same directory (~/test1/data/), but different file name (help.txt to helpToHead.txt) to change the name.
```

## htop

The `htop` could help you to check your tasks. This is a very important command help to manage the usage of server. 

```bash
htop -u tangmin02 # My user name is tangmin02, you need to change it to your user name.
```

> Press `q` to quit `htop`.

## Redirectors and wildcards

### Pipe `|`
A pipe (**`|`**) is used to connect multiple commands. It takes the _output_ from the previous command and “pipes” it into the _input_ of the following command.

- Count the number of files and directories in the current directory
	- Pipe the `ls` command into the `wc -l` command
	- `wc -l` is used to count the number of lines in its input
```bash
cd ~/test1/
ls | wc -l #
```

### Redirect  `>`
Redirect the output to a file, rather than just printing it to the screen.

- Write the output of **`ls`** to a new file called “directory_contents.txt”

```bash
cd ~/test1/
ls > directory_contents.txt
cat directory_contents.txt
```

-  Append an output to a file, rather than overwrite it, we can use two of them instead, **`>>`**:

```bash
cd ~/test1/data/
ls >> ~/test1/directory_contents.txt
cat ../directory_contents.txt
```

### Asterisk `*`
Represents any character appearing any number of times

```bash
ls *.txt
```

### Question mark `?`
Represents _any_ character that appears _only one time_.

```bash
cd ~/test1/
ls file?.txt
```

## Time-saving tips

>[!tips] Use `TAB`
>When typing in the Linux command line, just use `TAB` to autocomplete commands, filenames or folder names. Simply start typing. When you're ready press `TAB`. This is intuitive. The more you type, the more accurate the results will be.
>```bash
>cd ~
>cd t # If you press `TAB` now, the command is autocompleted as `cd test1/`
>```

>[!tips] Use $\uparrow$ and $\downarrow$ keys to browse history commands
>One of the time-saving features in Linux is the ability to browse through the history of recently executed commands. You can quickly retrieve and re-run previous commands without having to retype them by using $\uparrow$ and $\downarrow$ keys.
>- Press the $\uparrow$ key on your keyboard. This action will display the most recent command you executed.
>- To navigate forward in your command history, press the $\downarrow$ key. This will display the next command in your history.

# Metagenomics analysis pipeline

## Manage your working environment

In metagenomics analysis, effective working environment management is essential. Properly organizing your data in a structured manner will help you work efficiently. Before diving into analysis, create a clear folder structure in your home directory to organize your data and analysis results.

In this practical session, we will be following four sequential steps to analyze our metagenomic data: data retrieval, quality control, assembly, and annotation. To get started, let's create the three necessary folders in our working directory.

```bash
cd ~
mkdir metagenomics # Create the main working folder
cd metagenomics
mkdir 00.data # To store raw sequencing data & cleaned data
mkdir 01.assemble # To store assembled data
mkdir 02.annotation # To store annotated data

ll # Check whether the four folders are created succssfully
```

![[Screenshot 2023-10-28 at 16.25.29.png#pic_center|500]]

Tree view of current directory structure:

![[tree4.png#pic_center|500]]

## Step 1: Data retrieval

### Using Soft Links for Data Organization

In this section, you will learn how to create soft links to organize your data.

>[!info] Soft Link
>Soft links are symbolic references to files or directories.  In other words, a soft link is not a standard file, but a special file that points to an existing file. They are especially useful for managing and organizing your data without duplicating files. 

### Creating a Soft Link

To create a soft link, use the `ln -s` command followed by the source and target paths.

```bash
ln -s /path/to/source/file /path/to/target/link
```

Our raw data is located in the directory "/data/BIO215/metagenomics/". The sequencing method employed is paired-end, resulting in two files associated with one sample (NC001566.1), labeled as "R1" and "R2," respectively.

```bash
cd ~/metagenomics/00.data/ # Enter "00.data" folder

# Soft link the paired sequencing files from "/data/BIO215/metagenomics/" to our working directory `~/metagenomics/00.data/`
ln -s /data/BIO215/metagenomics/NC001566.1.R1.fq.gz ~/metagenomics/00.data/NC001566.1.R1.fq.gz
ln -s /data/BIO215/metagenomics/NC001566.1.R2.fq.gz ~/metagenomics/00.data/NC001566.1.R2.fq.gz

# Let's check whether the two files are soft linked successfully.
ll
```

![[Pasted image 20231027151456.png#pic_center|500]]

Tree view of current directory structure:

![[tree5.png#pic_center|500]]

## Step 2: Quality control by fastp

In this section, we will use [fastp](https://github.com/OpenGene/fastp) to conduct quality control for our sequence data. The resulting clean data will be stored in our "00.data" folder.

### fastp usage

To process both paired-end and single-end sequencing data by fastp, you must provide the sequencing file(s) to the fastp.  **Paired-end** data typically includes two files, while **single-end** data only consists of one file. Additionally, when specifying the output file name, it's common practice to append the term "**clean**" to the original sample name to indicate that the data has been cleaned.

For paired-end data (gzip compressed)

```bash
fastp -i in.R1.fq.gz -I in.R2.fq.gz -o out.R1.fq.gz -O out.R2.fq.gz
```

- This command processes the two **input files**, removes low-quality sequences, and trims adapters. And the resulting clean data is saved in the specified **output files**, respectively. 
-  Input Files:
	- `-i`: in.R1.fq.gz: Input file containing paired-end reads from the first read (R1).
	- `-I`: in.R2.fq.gz: Input file containing paired-end reads from the second read (R2)
-  Output Files:
	- `-o`: out.R1.fq.gz: Output file for the cleaned first read (R1).
	- `-O`: out.R2.fq.gz: Output file for the cleaned second read (R2).
- After running this command, you will find that the output folder contains several files, including two cleaned sequence files and a fastp report in HTML format.

For single-end data (not compressed)

```bash
fastp -i in.fq -o out.fq
```

Now, let's proceed to clean our data. 

>[!tips] Backslash `\`
>To enhance readability, we will employ the use of the backslash character `\` at each end of the command line. This instructs the system to interpret these multiple lines as a single input.

```bash
cd ~/metagenomics/01.data/ # Enter `01.data` folder

fastp \
    -i NC001566.1.R1.fq.gz \
	-o NC001566.1.clean.R1.fq.gz \
	-I NC001566.1.R2.fq.gz \
	-O NC001566.1.clean.R2.fq.gz \
	-q 20 -u 10 -w 16

# Quality Control Criteria (Parameter `-q`, `-u`, `-w`):
# -q: Specifies the quality threshold for filtering low-quality bases (default: 15). 
# -u: Specifies the minimum length for reads to be retained (default: 35). 
# -w: Specifies the window size for quality control sliding windows (default: 4).
```

- The `-q`, `-u`, and `-w` parameters allow you to define specific quality control criteria for your data.
- After running the command, you can access the "00.data" folder through the right panel of the RStudio server interface. Within this folder, you can open the `fastp.html` file to check and analyze the fastp report.

![[fastp.png#pic_center|500]]


## Step 3: Assembly by MEGIHIT

In this section, we will use [MEGAHIT](https://github.com/voutcn/megahit) to assemble our preprocessed and cleaned sequencing data. MEGAHIT is a metagenomic assembly tool that reconstructs genomes from sequencing data, particularly designed for metagenomic samples.

### MEGAHIT usage

```bash
megahit -1 pe_1.fq -2 pe_2.fq -o out
```

- This command uses the paired-end reads from R1 and R2 to generate contigs and scaffolds representing genomic sequences.
- Input Files:
	- `-1`: Input file containing paired-end reads from the first read (R1).
	- `-2`: Input file containing paired-end reads from the second read (R2).
- Output Directory:
	- `-o`: Output directory where MEGAHIT will save the assembled sequences and related files.
- After running this command, you can explore the result directory to access the assembly results, including contigs and various statistics related to the assembly process.

Now, let's assemble our sequence.

```bash
cd ~/metagenomics/01.assembly/ # Enter "01.assmebly" folder
megahit \
	-1 ~/metagenomics/00.data/NC001566.1.clean.R1.fq.gz \
	-2 ~/metagenomics/00.data/NC001566.1.clean.R2.fq.gz \
	--tmp-dir ./ \
	-m 0.8 \
	-t 1 \
	--k-list 31,51,71 \
	--no-mercy \
	-o NC001566.1

# Additional parameters:
# `-m`: Sets the memory usage limit to 80% (0.8) of available RAM (adjust as needed).
# `-t`: Specifies the number of threads or CPU cores to use during assembly (adjust as needed).
# `--k-list`: Specifies the list of k-mer sizes used for assembly (adjust as needed).
# `--no-mercy`: Disables "no-mercy" mode, which reduces memory consumption.
```

- After running the command, MEGAHIT will generate a folder with the name you specified using the `-o` parameter inside the "01.assembly" folder. Inside this folder, you'll find several files related to the assembly. The resulting assembled sequence is "**final.contigs.fa**".

![[megahit 1.png#pic_center|500]]

## Step 4: Annotation by MitoZ

In this section, we will use [MitoZ](https://github.com/linzhi2013/MitoZ) especially the `annotate` tool to perform the annotation of mitochondrial sequences within the sample NC001566.1. MitoZ is a versatile toolkit designed for the tasks of assembling, annotating, and visually presenting animal mitochondrial genomes, offering valuable insights into the characteristics of these genomes.

### Conda environment

Managing the dependencies and environment for MitoZ can be a complex task due to its comprehensive nature. Therefore, in this section, we've simplified the process by utilizing a dedicated Conda environment named "mitozEnv," which contains the configured version of MitoZ. This ensures a more convenient use of MitoZ.

>[!info] Conda environment
>A Conda environment is a self-contained and isolated workspace within the Conda package manager ecosystem. It allows you to manage and organize specific sets of software packages, libraries, and dependencies for your projects.

To initialize your conda, run the command `conda init bash`.

![[Pasted image 20231028140200.png#pic_center|500]]

To initialize Conda, execute the command `conda init bash`. Afterward, restart your terminal to activate the initialization. If you see `(base)` at the beginning of the command line prompt, it indicates that you have successfully initialized Conda and are now operating within the base environment.

![[restartterminal 1.png#pic_center|500]]

To access the "mitozEnv" environment, execute the command `conda activate mitozEnv`. If you observe a change from `(base)` to `(mitozEnv)` in your command line prompt, it indicates a successful transition to the MitoZ environment.

### MitoZ usage

```bash
mitoz annotate \
	--fastafile assembly.fa \
	--fq1 R1.fq.gz \
	--fq2 R2.fq.gz \
	--outprefix sample_name \
	--clade CLADE
```

- This command annotates the mitochondrial genome assembly (`assembly.fa`) using paired-end sequencing data (`R1.fq.gz` and `R2.fq.gz`).
	- Input files:
		- `--fastafile`: The file containing the mitochondrial genome assembly in FASTA format. MitoZ will use this assembly as a reference for the annotation process.
		- `--fq1` and `--fq2`: The files containing the paired-end reads. Both R1 and R2 reads are used to improve the accuracy of the mitochondrial genome annotation.
	- Output files:
		- `--outprefix`: Set the prefix for the output files that MitoZ generates during the annotation process.
	- Other parameters:
		- `--clade`: Used to specify the presence of a clade. In the context of mitochondrial genome annotation, a "clade" refers to a taxonomic group or lineage. By providing the `--clade` option and specifying the relevant clade name, MitoZ can tailor the annotation parameters to the characteristics of the mitochondrial genome within that taxonomic group.

Now, let's annotate the mitochondrial sequence in sample NC001566.1.

```bash
conda activate mitozEnv # Remember to enter the MitoZ environment first.

cd ~/metagenomics/02.annotation/

mitoz annotate \
	--fastafile ~/metagenomics/01.assembly/NC001566.1/final.contigs.fa \
	--fq1 ~/metagenomics/00.data/NC001566.1.clean.R1.fq.gz \
	--fq2 ~/metagenomics/00.data/NC001566.1.clean.R2.fq.gz \
	--outprefix NC001566.1 \
	--thread_number 1 \
	--clade Arthropoda
```

- In this particular case, we have configured the parameter `--thread_number` to "1" to optimize server resource usage, ensuring equitable access for all users. Additionally, as we are annotating the Arthropoda sequence, we have specified the parameter `--clade` to be "Arthropoda" to ensure that the annotation process is tailored to this specific taxonomic group.

>[!warning] MitoZ annotation
>The annotation process may take some time to complete, so please be patient. Additionally, it's important to note that at certain points during the process, the terminal may prompt you to press `ENTER` to proceed with the next step.

- Upon executing the command, MitoZ will generate two folders inside the "02.annotation" directory:
	  - "NC001566.1.final.contigs.fa.result": This folder stores the final results of the annotation process, including various annotation-related files.
	  - "tmp_NC001566.1_final.contigs.fa_mitoscaf.fa": This folder contains temporary files generated during the execution of MitoZ.
  - Within the final results folder, you'll find two visualization files ("circos.png" & "circos.svg") that provides a graphical representation of the mitochondrial sequence.
- To access summary information generated by MitoZ, you can use the `cat` command to view the contents of the "summary.txt" file, which provides an overview of the mitochondrial genome annotation results.

# Reference

- [Happy Belly Bioinformatics (UNIX)](https://astrobiomike.github.io/unix/)
- [TheMulQuaBio (UNIX and Linux)](https://mhasoba.github.io/TheMulQuaBio/notebooks/01-Unix.html)