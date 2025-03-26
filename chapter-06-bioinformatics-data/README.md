## Bioinformatics Data

This directory contains two fake data files: `gene-1.bed` and `gene-2.bed` to
illustrate how `diff` works.

## Code Examples for Case Study in Reproducibily Downloading Data

Many of these links are too long to fit in a page's width (and too logn to type
out too). I have included these code examples below to make it easier to copy
and paste.

    $ wget ftp://ftp.ensembl.org/pub/release-74/fasta/mus_musculus/dna/Mus_musculus.GRCm38.74.dna.toplevel.fa.gz

In your Markdown notes, this would be:

    Mouse (*Mus musculus*) reference genome version GRCm38 (Ensembl
    release 74) was downloaded on Sat Feb 22 21:24:42 PST 2014, using:

        wget ftp://ftp.ensembl.org/pub/release-74/fasta/mus_musculus/dna/Mus_musculus.GRCm38.74.dna.toplevel.fa.gz

Later on, I truncate some lines. These are the full lines:

    $ wget ftp://ftp.ensembl.org/pub/release-74/gtf/mus_musculus/Mus_musculus.GRCm38.74.gtf.gz
    $ wget ftp://ftp.ensembl.org/pub/release-74/gtf/mus_musculus/CHECKSUMS   ## grabs the checksums

The entire *README.md* file would look like:

    ## Genome and Annotation Data
    
    Mouse (*Mus musculus*) reference genome version GRCm38 (Ensembl
    release 74) was downloaded on Sat Feb 22 21:24:42 PST 2014, using:
    
        wget ftp://ftp.ensembl.org/pub/release-74/fasta/mus_musculus/dna/Mus_musculus.GRCm38.74.dna.toplevel.fa.gz
    
    Gene annotation data (also Ensembl release 74) was downloaded from Ensembl on
    Sat Feb 22 23:30:27 PST 2014, using:
    
        wget ftp://ftp.ensembl.org/pub/release-74/gtf/mus_musculus/Mus_musculus.GRCm38.74.gtf.gz
    
    ## SHA-1 Sums
    
     - `Mus_musculus.GRCm38.74.dna.toplevel.fa.gz`: 01c868e22a9815c0c8ac247c2154c20ae7899c5f
     - `Mus_musculus.GRCm38.74.gtf.gz`: cf5bb5f8bda2803410bb04b708bff59cb575e379

### EA notes 
following the book, I used these commands 
file is a gzipped FASTA file, so we can take a quick peek at all sequence headers by grepping for the regular expression "^>",
which matches all lines beginning with > (a FASTA header). 
We can use the zgrep program to extract the FASTA headers on this gzipped file
`$ zgrep "^>" Mus_musculus.GRCm38.74.dna.toplevel.fa.gz | less` 

`$ sum Mus_musculus.GRCm38.74.dna.toplevel.fa.gz`
