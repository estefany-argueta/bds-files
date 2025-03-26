# The Supplementary Material Repository for Bioinformatics Data Skills

This repository contains the supplementary files used in VB's book,
[Bioinformatics Data Skills](http://shop.oreilly.com/product/0636920030157.do),
published by O'Reilly Media. In addition to the supplementary files needed for
examples in the book, this repository contains:

 - Documentation on how all supplementary files were produced or how they were
   acquired.

 - Additional information readers may find interesting for each chapter. These
   are the `README.md` files in each chapter's directory. I've also included
   other resources like lists of recommended books for further learning.

 - Errata, and any necessary updates if materials become outdated for some
   reason.

Although I've made an strong, strong effort to focus on the subset of
bioinformatics tools that will not go out of date is this rapidly changing
field, if certain tools do become obsolete I will use this repository to host
and describe alternatives.

### EA Following Book 2025
chapter 5 on 20250325

### See Chapter 05 for github notes
There is a github script for pushing and a script to check for your gitignore file

### See Chapter 06 for more details
Checksums are compressed summaries of data -0 computed in a way that even if one bit of the data is changed, the checksums will be different. 
There are two types of checksums -- MD5 (older but common) and SHA-1 (newer and preferred). 

#### Using Shasum for Checksums
 echo "bioinformatics is fun" | shasum #you get one value

If we are downloading many files, it can get difficult to check each checksum individually. The program 'shasum' allows
us to complete and validate against a file containing the checksums of files. For example:
1. Create a SHA-1 checsum file for all files in a directory

shasum data/*fastq >fastq_checksums.sha
cat fastq_checksums.sha

2. Then we use shasums check option to validate that these files match the original versions

shasum -c fastq_checksum.sha

*EA Notes -- Found a different script to do checksums instead. Shasum wasn't working for comparing directories. Script lives in /home/scripts*

#### Compressing Files
`gzip` compresses files in place, replacing original uncompressed version with the compressed file. You can decompress files with `gunzip`
You can also output results to standard out (rather than chanign files in place) with the `-c` option. Example: `gzip -c in.fastq > in.fastq.gz`

If we want to concatenate gzip compressed output to an existing gzip file, we could do that. gzip -c in2.fastq >> in.fastq.gz
**Reminder we are using >> instead of the > which would overwrite our previous version raterh than append to it**
We could also get a better file if we comprss everything together -> `cat in.fastq in2.fastq | gzip > in.fastq.gz`
 

