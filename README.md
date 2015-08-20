# XenofilteR
Filtering of PDX samples for mouse derived reads

Human tumor samples, or cell lines, grown in immuno-deficient mice,
named xenografts, are a common model used in cancer research. Despite
its common use, genomic analysis of tumor material derived from
xenografts is challenging. The sequenced sample not only contains reads
that originate from the graft (human tumor or cell line) but also read
derived from host (mouse) stroma. Here we show the large effects the
host-derived sequence reads can have on downstream analysis of sequence
data from xenografts and developed a method to overcome these
challenges. Our tool, XenofilteR, assesses for each sequence read
whether it matches the graft or the host reference genome better, based
on mapping quality together with multiple values that indicate the edit
distance to the reference. XenofilteR output is a bam file with the
reads that map to mouse removed. We validated XenofilteR on in-silico
data and large sets of PDX samples, both DNA and RNA sequencing and show
our method outperforms existing methods.

## Bioconductor

XenofilteR will be submitted to Bioconductor.org. 


## Installation (not via Bioconductor)

Installation of XenofilteR should be performed as
follows:

    > source("http://bioconductor.org/biocLite.R")
    > biocLite(c("Rsamtools", "GenomicAlignments", "BiocParallel", "futile.logger"))

As the last step in the installation process, the latest XenofilteR package can
be downloaded from the
[XenoFilteR releases webpage](https://github.com/PeeperLab/XenoFilteR/releases)
and installed using the following command:

    $ R CMD INSTALL XenofilteR*.tar.gz

Now you are all set to start your analysis.

## XenofilteR usage:

Load the XenofilteR package in R using:

    > library("XenofilteR")

XenofilteR requires a dataframe or matrix, named 'Samplelist', with in the first 
column the bam file names as mapped to the graft reference. The second column contains the 
file names and paths to the bam files as mapped to the host reference. Each row in 
Sample_list represents a single sequence run or sample. 
The XenofilteR package and data are loaded in the following way: 

	> XenofilteR(Sample_list, destination.folder = "./", bp.param = bp.param)


## Contact
## 
We have tried to make the XenofilteR code readable and its use as easy
as possible. If any questions arise regarding the package, or if you
want to report any bugs, please do not hesitate and contact:

- [Oscar Krijgsman](mailto:o.krijgsman@nki.nl) 
- [Roel Kluin](mailto:r.kluin@nki.nl)

Oscar and Roel both work at the NKI, Oscar in the lab of Prof. Daniel
Peeper, Roel in the Genome Core Facility.


## Changes and additions we are currently working on
## 
- [ ] Making XenofilteR into an R-package 
- [x] Initial loop running the basic function of XenofilteR

