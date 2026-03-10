3 ways to Change Directories to Home
1. cd $HOME
2. cd ~
3. cd ../../../

How to list files in /bin starting with certain letters
1. ls /bin/c* ls /bin/ | grep '^c'
Command to find the line number in your history
1. ls /bin/c* | ws -l

How to navigate to home and list contents of a directory from there
1. ls -F gen711-811/shell_data/untrimmed_fastq/

Navigate to a directory an list hidden directories
1. ls --all .hidden/
2. ls -a
3. ls -la
4. ls -laF (long format, include security settings for files)
5. ls .*

Find the line number in your history for the command that listed .sh files in /user/bin
1. ls /usr/bin/*.sh
2. ls /usr/binc* | wc -l

Print out the contents of a .fastq file, find the last line
1. cat NAME.fastq
2. tail -n1 NAME.fastq (or use -n4 if you want the full read of fastq file)

In a .fastq file, find the next nucleotides after the first instance of TTTT
1. less NAME.fasta 
2. less -S NAME.fasta /TTTT
3. grep 'TTTT' *fastq

Format of file permissions
1. (file type)(user)(group)(other)
2. rwx is read, write, execute permissions

View and change file permissions
1. ls -l (to view)
2. chmod

Create backups of fastq files
1. mkdir backup
2. cp NAMEofFILE NEWNAMEofCOPY
3. mc *backup.fastq backup/

