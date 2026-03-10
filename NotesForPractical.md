### Notes for Practical #1

**3 ways to Change Directories to Home**
1. cd $HOME
2. cd ~
3. cd ../../../

**How to list files in /bin starting with certain letters**
1. ls /bin/c* ls /bin/ | grep '^c'
Command to find the line number in your history
2. ls /bin/c* | ws -l

**How to navigate to home and list contents of a directory from there**
1. ls -F gen711-811/shell_data/untrimmed_fastq/

**Navigate to a directory an list hidden directories**
1. ls --all .hidden/
2. ls -a
3. ls -la
4. ls -laF (long format, include security settings for files)
5. ls .*

**Find the line number in your history for the command that listed .sh files in /user/bin**
1. ls /usr/bin/*.sh
2. ls /usr/binc* | wc -l

**Print out the contents of a .fastq file, find the last line**
1. cat NAME.fastq
2. tail -n1 NAME.fastq (or use -n4 if you want the full read of fastq file)

**In a .fastq file, find the next nucleotides after the first instance of TTTT**
1. less NAME.fasta 
2. less -S NAME.fasta /TTTT
3. grep 'TTTT' *fastq

**Format of file permissions**
* (file type)(user)(group)(other)
* rwx is read, write, execute permissions

**View and change file permissions**
1. ls -l (to view)
2. chmod (permission) FILE.fastq
3. adding -w will make the file write-protected
4. adding ug+rwx specifies user and group and gives rwx permissions

**Create backups of fastq files**
1. mkdir backup
2. cp NAMEofFILE NEWNAMEofCOPY
3. mc *backup.fastq backup/

**How to find size of fastq file**
* ls -l -h

**Load a conda environment and find where a program called 'fastqc' is stored**
1. activate genomics (load conda called genomics)

```
fastqc *.fastq*
```

**Unzip a zipped file**
1. *zip

**Searcing within a file using combined commands**
1. grep -A1 -h '@SRR' *fastq (searches files ending in fastq with the header line @SRR, -A1 displays one line after each match, -h suppresses names)
2. grep -A1 -h '@SRR' *fastq | grep -v '^--' | grep -v '^@SRR'

**Search a fastq file for a nucleotide sequence and return matching lines with the name for each sequence**
1. grep -B1 "GNATNAC" NAME.fastq (for a single specific file)
2. grep -B "GNATNAC" *.fastq (to search all fastq files)

**Make a file called 'bad-read.fastq' made up of poor fastq reads**
1. grep -B1 -A2 'NNNNNNNNNN' NAME.fastq > bad-reas.fastq

**How many sequences are there in NAME.fastq file, considering there are 4 lines per sequence**
1. wc -l NAME.fastq
2. divide the count by 4

**Find how many sequences are in a fastq file with at least 3 consecutive Ns**
1. grep NNN NAME.fastq | wc -l

**Remove _2026 from all .txt files**
1. for filename in *.fasta
2. do
3. echo -e name=$ (basename ${filename}.fastq)
4. echo -e mv ${filename} ${name}_2026.tx
5. done

**When wanting the script to tell us when it's done**
1. for name in *.fastq
2. do
3. echo ${name}
4. done
- above is the same as saying echo NAME.fastq echo NAME2.fastq
1. for fq in *.fastq
2. do
3. wc -l ${fq}
4. done
- 
1. for filenmae in *.fastq
2. do
3. head -n 2 ${filename}
4. done
